---
title: Migrar a .NET Core - mediante el paquete de compatibilidad de Windows
description: "Obtenga información sobre el paquete de compatibilidad de Windows y cómo puede utilizarlo para puerto código existente de .NET Framework a .NET Core"
keywords: . NET, .NET core, Windows, compatibilidad
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="7a7bf-104">Con el paquete de compatibilidad de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="7a7bf-105">Uno de los problemas más comunes que se enfrentan los programadores al trasladar su código existente a .NET Core es que dependen de las API y las tecnologías que solo existen en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="7a7bf-106">El *paquete de compatibilidad de Windows* consiste en proporcionar muchas de estas tecnologías para que compilar aplicaciones de .NET Core, así como bibliotecas estándar de .NET pasa a ser mucho más viable para código existente.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="7a7bf-107">Este paquete es un valor lógico [extensión del estándar de .NET 2.0](../whats-new/index.md#api-changes-and-library-support) que significativamente aumenta conjunto de API y el código existente se compila con casi ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="7a7bf-108">Pero con el fin de mantener la promesa de .NET estándar ("es el conjunto de API que proporcionan todas las implementaciones. NET"), esto no incluye tecnologías que no pueden funcionar en todas las plataformas, como el registro, Windows Management Instrumentation (WMI), o la emisión de reflexión API.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="7a7bf-109">El *paquete de compatibilidad de Windows* se ubica en la parte superior del estándar de .NET y proporciona acceso a las tecnologías que sean sólo de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="7a7bf-110">Es especialmente útil para los clientes que desean migrar a .NET Core sino que planifique permanezca en Windows como primer paso.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="7a7bf-111">En ese caso, la imposibilidad de usar tecnologías solo de Windows es sólo un obstáculo de migración con cero ventajas arquitectónicas.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="7a7bf-112">Contenido del paquete</span><span class="sxs-lookup"><span data-stu-id="7a7bf-112">Package contents</span></span>

<span data-ttu-id="7a7bf-113">El *paquete de compatibilidad de Windows* se proporciona mediante el paquete de NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) y puede hacer referencia desde proyectos destinados a .NET Core o .NET estándar.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="7a7bf-114">Proporciona unos 20.000 API, incluidas las API de solo de Windows, así como entre plataformas de las siguientes áreas de tecnología:</span><span class="sxs-lookup"><span data-stu-id="7a7bf-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="7a7bf-115">Páginas de códigos</span><span class="sxs-lookup"><span data-stu-id="7a7bf-115">Code Pages</span></span>
* <span data-ttu-id="7a7bf-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="7a7bf-116">CodeDom</span></span>
* <span data-ttu-id="7a7bf-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="7a7bf-117">Configuration</span></span>
* <span data-ttu-id="7a7bf-118">Servicios de directorio</span><span class="sxs-lookup"><span data-stu-id="7a7bf-118">Directory Services</span></span>
* <span data-ttu-id="7a7bf-119">dibujo</span><span class="sxs-lookup"><span data-stu-id="7a7bf-119">Drawing</span></span>
* <span data-ttu-id="7a7bf-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="7a7bf-120">ODBC</span></span>
* <span data-ttu-id="7a7bf-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="7a7bf-121">Permissions</span></span>
* <span data-ttu-id="7a7bf-122">Puertos</span><span class="sxs-lookup"><span data-stu-id="7a7bf-122">Ports</span></span>
* <span data-ttu-id="7a7bf-123">Listas de Control de acceso (ACL) de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="7a7bf-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="7a7bf-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="7a7bf-125">Criptografía de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-125">Windows Cryptography</span></span>
* <span data-ttu-id="7a7bf-126">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-126">Windows EventLog</span></span>
* <span data-ttu-id="7a7bf-127">Instrumental de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="7a7bf-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="7a7bf-128">Contadores de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-128">Windows Performance Counters</span></span>
* <span data-ttu-id="7a7bf-129">Registro de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-129">Windows Registry</span></span>
* <span data-ttu-id="7a7bf-130">Almacenamiento en caché de tiempo de ejecución de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="7a7bf-131">servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="7a7bf-131">Windows Services</span></span>

<span data-ttu-id="7a7bf-132">Para obtener más información, consulte el [especificaciones del módulo de compatibilidad de](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7a7bf-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="7a7bf-133">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="7a7bf-133">Get started</span></span>

1. <span data-ttu-id="7a7bf-134">Antes de migrar, asegúrese de echar un vistazo a la [proceso de migración](index.md).</span><span class="sxs-lookup"><span data-stu-id="7a7bf-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="7a7bf-135">Al migrar código existente a .NET Core o .NET estándar, instale el paquete de NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="7a7bf-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="7a7bf-136">Si desea permanecer en Windows, que tiene todo listo.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="7a7bf-137">Si desea ejecutar la aplicación de .NET Core o la biblioteca estándar de .NET en Linux o Mac OS, utilice la [API analizador](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) para encontrar el uso de API que no funcionarán entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="7a7bf-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="7a7bf-138">Quite los usos de estas API, reemplácelas con alternativas de multiplataforma o protegerse con una comprobación de la plataforma, como:</span><span class="sxs-lookup"><span data-stu-id="7a7bf-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="7a7bf-139">Para obtener una demostración, visite la [vídeo de Channel 9 del paquete de compatibilidad de Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="7a7bf-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
