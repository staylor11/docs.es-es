---
title: "Aplicaciones monolíticas containerizing"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Aplicaciones monolíticas containerizing"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 11e2c24403b9b61584e424696c844e00e5d34b03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="containerizing-monolithic-applications"></a><span data-ttu-id="36d82-104">Aplicaciones monolíticas containerizing</span><span class="sxs-lookup"><span data-stu-id="36d82-104">Containerizing monolithic applications</span></span>

<span data-ttu-id="36d82-105">Puede compilar una aplicación web único, monolithically implementado o servicio e implementarlo como un contenedor.</span><span class="sxs-lookup"><span data-stu-id="36d82-105">You might want to build a single, monolithically deployed web application or service and deploy it as a container.</span></span> <span data-ttu-id="36d82-106">La propia aplicación podría no ser internamente monolítica pero había estructurado como varias bibliotecas, componentes o incluso las capas (nivel de aplicación, el nivel de dominio, capa de acceso a datos, etcetera).</span><span class="sxs-lookup"><span data-stu-id="36d82-106">The application itself might not be internally monolithic, but structured as several libraries, components, or even layers (application layer, domain layer, data-access layer, etc.).</span></span> <span data-ttu-id="36d82-107">Externamente, sin embargo, es un contenedor único, un proceso único, una sola aplicación web o un servicio único.</span><span class="sxs-lookup"><span data-stu-id="36d82-107">Externally, however, it is a single container—a single process, a single web application, or a single service.</span></span>

<span data-ttu-id="36d82-108">Para administrar este modelo, implementa un único contenedor para representar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36d82-108">To manage this model, you deploy a single container to represent the application.</span></span> <span data-ttu-id="36d82-109">Para escalar verticalmente, solo tiene que agregar más copias con un equilibrador de carga en la parte frontal.</span><span class="sxs-lookup"><span data-stu-id="36d82-109">To scale up, you just add more copies with a load balancer in front.</span></span> <span data-ttu-id="36d82-110">La simplicidad proviene de administrar una única implementación en un único contenedor o la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="36d82-110">The simplicity comes from managing a single deployment in a single container or VM.</span></span>

![](./media/image1.png)

<span data-ttu-id="36d82-111">**Figura 4-1**.</span><span class="sxs-lookup"><span data-stu-id="36d82-111">**Figure 4-1**.</span></span> <span data-ttu-id="36d82-112">Ejemplo de la arquitectura de una aplicación monolítica en contenedores</span><span class="sxs-lookup"><span data-stu-id="36d82-112">Example of the architecture of a containerized monolithic application</span></span>

<span data-ttu-id="36d82-113">Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1.</span><span class="sxs-lookup"><span data-stu-id="36d82-113">You can include multiple components, libraries, or internal layers in each container, as illustrated in Figure 4-1.</span></span> <span data-ttu-id="36d82-114">Sin embargo, este patrón monolítico puede entrar en conflicto con el principio de contenedor "un contenedor realiza una acción y no en un proceso", pero podrían ser correcta para algunos de los casos.</span><span class="sxs-lookup"><span data-stu-id="36d82-114">However, this monolithic pattern might conflict with the container principle “a container does one thing, and does it in one process”, but might be ok for some cases.</span></span>

<span data-ttu-id="36d82-115">El inconveniente de este enfoque se vuelve evidente si aumenta la aplicación, que requiere una ampliación.</span><span class="sxs-lookup"><span data-stu-id="36d82-115">The downside of this approach becomes evident if the application grows, requiring it to scale.</span></span> <span data-ttu-id="36d82-116">Si puede escalar toda la aplicación, no es realmente un problema.</span><span class="sxs-lookup"><span data-stu-id="36d82-116">If the entire application can scale, it is not really a problem.</span></span> <span data-ttu-id="36d82-117">Sin embargo, en la mayoría de los casos, unos pocos elementos de la aplicación son los puntos de retracción que necesidad de ajuste de escala, mientras que otros componentes son utiliza menos.</span><span class="sxs-lookup"><span data-stu-id="36d82-117">However, in most cases, just a few parts of the application are the choke points that requiring scaling, while other components are used less.</span></span>

<span data-ttu-id="36d82-118">Por ejemplo, en una aplicación típica de comercio electrónico, es probable que deba escalar el subsistema de información de producto, dado que muchos clientes más examinar productos de adquirirlas.</span><span class="sxs-lookup"><span data-stu-id="36d82-118">For example, in a typical e-commerce application, you likely need to scale the product information subsystem, because many more customers browse products than purchase them.</span></span> <span data-ttu-id="36d82-119">Más clientes utilice su cesta de usar la canalización de pago.</span><span class="sxs-lookup"><span data-stu-id="36d82-119">More customers use their basket than use the payment pipeline.</span></span> <span data-ttu-id="36d82-120">Los clientes menos agreguen comentarios o ver su historial de compras.</span><span class="sxs-lookup"><span data-stu-id="36d82-120">Fewer customers add comments or view their purchase history.</span></span> <span data-ttu-id="36d82-121">Y es posible que tenga solo un conjunto de empleados, que necesita para administrar el contenido y las campañas de marketing.</span><span class="sxs-lookup"><span data-stu-id="36d82-121">And you might have only a handful of employees, that need to manage the content and marketing campaigns.</span></span> <span data-ttu-id="36d82-122">Si ajusta el diseño monolítico, todo el código para estas tareas se implementa varias veces y escalar en el mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="36d82-122">If you scale the monolithic design, all the code for these different tasks is deployed multiple times and scaled at the same grade.</span></span>

<span data-ttu-id="36d82-123">Hay varias formas de escalar una aplicación: duplicación horizontal, división de diferentes áreas de la aplicación y partición conceptos similares de negocio o sus datos.</span><span class="sxs-lookup"><span data-stu-id="36d82-123">There are multiple ways to scale an application—horizontal duplication, splitting different areas of the application, and partitioning similar business concepts or data.</span></span> <span data-ttu-id="36d82-124">Pero, además del problema de ajuste de escala en todos los componentes, requieren cambios en un único componente al volver a examinar completa de toda la aplicación y una implementación completa de todas las instancias.</span><span class="sxs-lookup"><span data-stu-id="36d82-124">But, in addition to the problem of scaling all components, changes to a single component require complete retesting of the entire application, and a complete redeployment of all the instances.</span></span>

<span data-ttu-id="36d82-125">Sin embargo, el enfoque monolítico es común, porque el desarrollo de la aplicación es inicialmente más fácil que para microservicios enfoques.</span><span class="sxs-lookup"><span data-stu-id="36d82-125">However, the monolithic approach is common, because the development of the application is initially easier than for microservices approaches.</span></span> <span data-ttu-id="36d82-126">Por lo tanto, muchas organizaciones desarrollan con este enfoque de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="36d82-126">Thus, many organizations develop using this architectural approach.</span></span> <span data-ttu-id="36d82-127">Mientras que algunas organizaciones han tenido bueno suficientes resultados, otros están alcanzando límites.</span><span class="sxs-lookup"><span data-stu-id="36d82-127">While some organizations have had good enough results, others are hitting limits.</span></span> <span data-ttu-id="36d82-128">Muchas organizaciones diseñado sus aplicaciones mediante este modelo ya infraestructura y herramientas de hecho demasiado difícil compilar el servicio orientada a servicios (SOA) de arquitecturas hace años, y no verán la necesidad, hasta que la aplicación ha crecido.</span><span class="sxs-lookup"><span data-stu-id="36d82-128">Many organizations designed their applications using this model because tools and infrastructure made it too difficult to build service oriented architectures (SOA) years ago, and they did not see the need—until the application grew.</span></span>

<span data-ttu-id="36d82-129">Desde una perspectiva de la infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tienen una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.</span><span class="sxs-lookup"><span data-stu-id="36d82-129">From an infrastructure perspective, each server can run many applications within the same host and have an acceptable ratio of efficiency in resources usage, as shown in Figure 4-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="36d82-130">**Figura 4-2**.</span><span class="sxs-lookup"><span data-stu-id="36d82-130">**Figure 4-2**.</span></span> <span data-ttu-id="36d82-131">Enfoque monolítico: Host ejecuta varias aplicaciones, cada aplicación se ejecuta como un contenedor</span><span class="sxs-lookup"><span data-stu-id="36d82-131">Monolithic approach: Host running multiple apps, each app running as a container</span></span>

<span data-ttu-id="36d82-132">Monolíticas aplicaciones en Microsoft Azure se pueden implementar con máquinas virtuales dedicadas para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="36d82-132">Monolithic applications in Microsoft Azure can be deployed using dedicated VMs for each instance.</span></span> <span data-ttu-id="36d82-133">Además, para usar [conjuntos de escalas de VM de Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="36d82-133">Additionally, using [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), you can easily scale the VMs.</span></span> <span data-ttu-id="36d82-134">[Servicio de aplicaciones de Azure](https://azure.microsoft.com/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="36d82-134">[Azure App Service](https://azure.microsoft.com/services/app-service/) can also run monolithic applications and easily scale instances without requiring you to manage the VMs.</span></span> <span data-ttu-id="36d82-135">A partir de 2016, servicios de aplicaciones de Azure puede ejecuta instancias únicas de contenedores de Docker, simplificar la implementación.</span><span class="sxs-lookup"><span data-stu-id="36d82-135">Since 2016, Azure App Services can run single instances of Docker containers as well, simplifying deployment.</span></span>

<span data-ttu-id="36d82-136">Como un entorno de preguntas y respuestas o un entorno de producción limitado, puede implementar varios host de Docker las máquinas virtuales y equilibrar con el equilibrador de Azure, tal como se muestra en la figura 4-3.</span><span class="sxs-lookup"><span data-stu-id="36d82-136">As a QA environment or a limited production environment, you can deploy multiple Docker host VMs and balance them using the Azure balancer, as shown in Figure 4-3.</span></span> <span data-ttu-id="36d82-137">Esto le permite administrar escalado con un enfoque más generales, porque toda la aplicación reside dentro de un único contenedor.</span><span class="sxs-lookup"><span data-stu-id="36d82-137">This lets you manage scaling with a coarse-grain approach, because the whole application lives within a single container.</span></span>

![](./media/image3.png)

<span data-ttu-id="36d82-138">**Figura 4-3**.</span><span class="sxs-lookup"><span data-stu-id="36d82-138">**Figure 4-3**.</span></span> <span data-ttu-id="36d82-139">Ejemplo de varios hosts de escalado de una aplicación de contenedor único</span><span class="sxs-lookup"><span data-stu-id="36d82-139">Example of multiple hosts scaling up a single container application</span></span>

<span data-ttu-id="36d82-140">Implementación a los distintos hosts puede administrarse con técnicas de implementación tradicionales.</span><span class="sxs-lookup"><span data-stu-id="36d82-140">Deployment to the various hosts can be managed with traditional deployment techniques.</span></span> <span data-ttu-id="36d82-141">Docker hosts pueden administrarse con comandos como `docker run` o `docker-compose` lleva a cabo manualmente o a través de automatización como las canalizaciones de entrega continua (CD).</span><span class="sxs-lookup"><span data-stu-id="36d82-141">Docker hosts can be managed with commands like `docker run` or `docker-compose` performed manually, or through automation such as continuous delivery (CD) pipelines.</span></span>

## <a name="deploying-a-monolithic-application-as-a-container"></a><span data-ttu-id="36d82-142">Implementar una aplicación monolítica como un contenedor</span><span class="sxs-lookup"><span data-stu-id="36d82-142">Deploying a monolithic application as a container</span></span>

<span data-ttu-id="36d82-143">Hay ventajas derivadas del uso de contenedores para administrar las implementaciones de aplicaciones monolítico.</span><span class="sxs-lookup"><span data-stu-id="36d82-143">There are benefits to using containers to manage monolithic application deployments.</span></span> <span data-ttu-id="36d82-144">Ajuste de escala en instancias de contenedor es mucho más rápido y fácil de implementar máquinas virtuales adicionales.</span><span class="sxs-lookup"><span data-stu-id="36d82-144">Scaling container instances is far faster and easier than deploying additional VMs.</span></span> <span data-ttu-id="36d82-145">Incluso si usa conjuntos de escalas de máquina virtual, máquinas virtuales tardan tiempo en iniciarse.</span><span class="sxs-lookup"><span data-stu-id="36d82-145">Even if you use VM Scale Sets, VMs take time to start.</span></span> <span data-ttu-id="36d82-146">Cuando se implementa como instancias de aplicación tradicional en lugar de contenedores, la configuración de la aplicación se administra como parte de la máquina virtual, lo que no es ideal.</span><span class="sxs-lookup"><span data-stu-id="36d82-146">When deployed as traditional application instances instead of containers, the configuration of the application is managed as part of the VM, which is not ideal.</span></span>

<span data-ttu-id="36d82-147">Implementación de actualizaciones como imágenes de Docker es mucho más rápido y eficaz de la red.</span><span class="sxs-lookup"><span data-stu-id="36d82-147">Deploying updates as Docker images is far faster and network efficient.</span></span> <span data-ttu-id="36d82-148">Las imágenes de docker inician normalmente en segundos, lo que acelera la implementación.</span><span class="sxs-lookup"><span data-stu-id="36d82-148">Docker images typically start in seconds, which speeds rollouts.</span></span> <span data-ttu-id="36d82-149">Anular una instancia de la imagen de Docker es tan fácil como emitir un `docker stop` de comandos y normalmente se completa en menos de un segundo.</span><span class="sxs-lookup"><span data-stu-id="36d82-149">Tearing down a Docker image instance is as easy as issuing a `docker stop` command, and typically completes in less than a second.</span></span>

<span data-ttu-id="36d82-150">Dado que los contenedores son inmutables por diseño, nunca necesite preocuparse sobre máquinas virtuales están dañadas.</span><span class="sxs-lookup"><span data-stu-id="36d82-150">Because containers are immutable by design, you never need to worry about corrupted VMs.</span></span> <span data-ttu-id="36d82-151">En cambio, las secuencias de comandos de actualización para una máquina virtual podrían olvidar para tener en cuenta algunas configuración específica o un archivo restante en el disco.</span><span class="sxs-lookup"><span data-stu-id="36d82-151">In contrast, update scripts for a VM might forget to account for some specific configuration or file left on disk.</span></span>

<span data-ttu-id="36d82-152">Mientras monolíticas aplicaciones pueden beneficiarse de Docker, nos estamos tocar solo en los beneficios.</span><span class="sxs-lookup"><span data-stu-id="36d82-152">While monolithic applications can benefit from Docker, we are touching only on the benefits.</span></span> <span data-ttu-id="36d82-153">Ventajas adicionales de administración de contenedores de proceden de la implementación con orchestrators de contenedor, que administración las distintas instancias y ciclo de vida de cada instancia del contenedor.</span><span class="sxs-lookup"><span data-stu-id="36d82-153">Additional benefits of managing containers come from deploying with container orchestrators, which manage the various instances and lifecycle of each container instance.</span></span> <span data-ttu-id="36d82-154">Es el punto de entrada en el dominio Kerberos de microservicios interrumpir la aplicación monolítico en subsistemas que se pueden escalar, desarrollar e implementar de forma individual.</span><span class="sxs-lookup"><span data-stu-id="36d82-154">Breaking up the monolithic application into subsystems that can be scaled, developed, and deployed individually is your entry point into the realm of microservices.</span></span>

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a><span data-ttu-id="36d82-155">Publicar una aplicación sencilla basada en contenedor al servicio de aplicaciones de Azure</span><span class="sxs-lookup"><span data-stu-id="36d82-155">Publishing a single-container-based application to Azure App Service</span></span>

<span data-ttu-id="36d82-156">Si desea obtener la validación de un contenedor de implementada en Azure o cuando una aplicación es simplemente una aplicación de contenedor único, servicio de aplicaciones de Azure proporciona una excelente manera de proporcionar servicios escalables destinados a sencilla basada en contenedor.</span><span class="sxs-lookup"><span data-stu-id="36d82-156">Whether you want to get validation of a container deployed to Azure or when an application is simply a single-container application, Azure App Service provides a great way to provide scalable single-container-based services.</span></span> <span data-ttu-id="36d82-157">Con el servicio de aplicación de Azure es sencillo.</span><span class="sxs-lookup"><span data-stu-id="36d82-157">Using Azure App Service is simple.</span></span> <span data-ttu-id="36d82-158">Proporciona integración excelente con Git que resulte sencillo tomar el código, se crean en Visual Studio e impleméntelo directamente en Azure.</span><span class="sxs-lookup"><span data-stu-id="36d82-158">It provides great integration with Git to make it easy to take your code, build it in Visual Studio, and deploy it directly to Azure.</span></span>

![](./media/image4.png)

<span data-ttu-id="36d82-159">**Figura 4-4**.</span><span class="sxs-lookup"><span data-stu-id="36d82-159">**Figure 4-4**.</span></span> <span data-ttu-id="36d82-160">Publicar una aplicación de contenedor único al servicio de aplicaciones de Azure desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="36d82-160">Publishing a single-container application to Azure App Service from Visual Studio</span></span>

<span data-ttu-id="36d82-161">Sin Docker, si necesita otras funcionalidades, marcos o dependencias que no son compatibles con el servicio de aplicación de Azure, se han tenido que esperar hasta que el equipo de Azure actualiza esas dependencias en el servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="36d82-161">Without Docker, if you needed other capabilities, frameworks, or dependencies that are not supported in Azure App Service, you had to wait until the Azure team updated those dependencies in App Service.</span></span> <span data-ttu-id="36d82-162">O bien, tiene que cambiar a otros servicios como Azure Service Fabric, servicios en la nube o incluso las máquinas virtuales, donde había aún más control y podría instalar un componente necesario o el marco de trabajo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36d82-162">Or you had to switch to other services like Azure Service Fabric, Azure Cloud Services, or even VMs, where you had further control and you could install a required component or framework for your application.</span></span>

<span data-ttu-id="36d82-163">Compatibilidad con el contenedor de 2017 de Visual Studio ofrece la capacidad para incluir todo lo que desees en el entorno de aplicación, tal como se muestra en la figura 4-4.</span><span class="sxs-lookup"><span data-stu-id="36d82-163">Container support in Visual Studio 2017 gives you the ability to include whatever you want in your application environment, as shown in Figure 4-4.</span></span> <span data-ttu-id="36d82-164">Puesto que se está ejecutando en un contenedor, si agrega una dependencia a la aplicación, puede incluir la dependencia en la imagen de Dockerfile o Docker.</span><span class="sxs-lookup"><span data-stu-id="36d82-164">Since you are running it in a container, if you add a dependency to your application, you can include the dependency in your Dockerfile or Docker image.</span></span>

<span data-ttu-id="36d82-165">Como también se muestra en la figura 4-4, el flujo de publicación inserta una imagen a través de un registro de contenedor.</span><span class="sxs-lookup"><span data-stu-id="36d82-165">As also shown in Figure 4-4, the publish flow pushes an image through a container registry.</span></span> <span data-ttu-id="36d82-166">Esto puede ser el registro de contenedor de Azure (en un registro de cierre a las implementaciones en Azure y protegido por las cuentas y grupos de Active Directory de Azure), o cualquier otro registro de Docker, como Docker Hub o un registro local.</span><span class="sxs-lookup"><span data-stu-id="36d82-166">This can be the Azure Container Registry (a registry close to your deployments in Azure and secured by Azure Active Directory groups and accounts), or any other Docker registry, like Docker Hub or an on-premises registry.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="36d82-167">[Anterior] (index.md) [siguiente] (docker-aplicaciones-estado-data.md)</span><span class="sxs-lookup"><span data-stu-id="36d82-167">[Previous] (index.md) [Next] (docker-application-state-data.md)</span></span>