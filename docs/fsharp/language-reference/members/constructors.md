---
title: Constructores (F#)
description: "Obtener información sobre cómo definir y utilizar constructores en F # para crear e inicializar objetos de clase y estructura."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e0da2250-29de-4145-a1be-e5faff080759
ms.openlocfilehash: 60ed93f1c1dc15e99465d969c9e4fd3e61c28ffa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="constructors"></a><span data-ttu-id="23376-104">Constructores</span><span class="sxs-lookup"><span data-stu-id="23376-104">Constructors</span></span>

<span data-ttu-id="23376-105">En este tema se describe cómo definir y utilizar los constructores para crear e inicializar objetos de clase y estructura.</span><span class="sxs-lookup"><span data-stu-id="23376-105">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="23376-106">Construcción de objetos de clase</span><span class="sxs-lookup"><span data-stu-id="23376-106">Construction of Class Objects</span></span>
<span data-ttu-id="23376-107">Objetos de tipos de clase tienen constructores.</span><span class="sxs-lookup"><span data-stu-id="23376-107">Objects of class types have constructors.</span></span> <span data-ttu-id="23376-108">Hay dos tipos de constructores.</span><span class="sxs-lookup"><span data-stu-id="23376-108">There are two kinds of constructors.</span></span> <span data-ttu-id="23376-109">Uno es el constructor primario, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="23376-109">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="23376-110">Especificar otros constructores adicionales opcionales mediante la `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="23376-110">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="23376-111">Todos estos constructores adicionales deben llamar al constructor primario.</span><span class="sxs-lookup"><span data-stu-id="23376-111">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="23376-112">El constructor primario contiene `let` y `do` enlaces que aparecen al principio de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="23376-112">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="23376-113">A `let` enlace declara campos privados y los métodos de la clase; un `do` enlace ejecuta código.</span><span class="sxs-lookup"><span data-stu-id="23376-113">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="23376-114">Para obtener más información acerca de `let` enlaces en los constructores de clase, consulte [ `let` enlaces en clases](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="23376-114">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="23376-115">Para obtener más información acerca de `do` enlaces en los constructores, vea [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="23376-115">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="23376-116">Independientemente de si el constructor que desea llamar es un constructor primario o un constructor adicional, puede crear objetos mediante un `new` expresión, con o sin la parte opcional `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="23376-116">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="23376-117">Inicializar los objetos junto con los argumentos de constructor, ya sea mediante la lista de los argumentos en orden y separados por comas y entre paréntesis, o mediante el uso de argumentos con nombre y los valores entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="23376-117">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="23376-118">También puede establecer propiedades en un objeto durante la construcción del objeto mediante el uso de los nombres de propiedad y asignar los valores tal y como se utiliza con nombre argumentos de constructor.</span><span class="sxs-lookup"><span data-stu-id="23376-118">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="23376-119">El código siguiente muestra una clase que tiene un constructor y varias maneras de crear objetos.</span><span class="sxs-lookup"><span data-stu-id="23376-119">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="23376-120">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="23376-120">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="23376-121">Construcción de estructuras</span><span class="sxs-lookup"><span data-stu-id="23376-121">Construction of Structures</span></span>
<span data-ttu-id="23376-122">Las estructuras siguen todas las reglas de clases.</span><span class="sxs-lookup"><span data-stu-id="23376-122">Structures follow all the rules of classes.</span></span> <span data-ttu-id="23376-123">Por lo tanto, puede tener un constructor primario, y puede proporcionar constructores adicionales mediante `new`.</span><span class="sxs-lookup"><span data-stu-id="23376-123">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="23376-124">Sin embargo, hay una diferencia importante entre las estructuras y clases: las estructuras pueden tener un constructor predeterminado (es decir, uno sin argumentos), aunque se haya definido ningún constructor primario.</span><span class="sxs-lookup"><span data-stu-id="23376-124">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="23376-125">El constructor predeterminado inicializa todos los campos en el valor predeterminado para ese tipo, normalmente cero o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="23376-125">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="23376-126">Los constructores que se definen para las estructuras de deben tener al menos un argumento para que no entren en conflicto con el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="23376-126">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="23376-127">Además, las estructuras suelen tienen campos que se crean mediante el `val` palabra clave; las clases también pueden tener estos campos.</span><span class="sxs-lookup"><span data-stu-id="23376-127">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="23376-128">Estructuras y clases que tienen campos definidos mediante el `val` palabra clave también se puede inicializar en constructores adicionales mediante expresiones de registro, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="23376-128">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="23376-129">Para obtener más información, consulte [campos explícitos: el `val` palabra clave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="23376-129">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="23376-130">Ejecutar efectos secundarios en constructores</span><span class="sxs-lookup"><span data-stu-id="23376-130">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="23376-131">Un constructor primario en una clase puede ejecutar código en un `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="23376-131">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="23376-132">Sin embargo, ¿qué ocurre si tiene que ejecutar el código en un constructor adicional, sin un `do` enlace?</span><span class="sxs-lookup"><span data-stu-id="23376-132">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="23376-133">Para ello, use la `then` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="23376-133">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="23376-134">Los efectos secundarios del constructor primario seguir ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="23376-134">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="23376-135">Por lo tanto, el resultado es como sigue.</span><span class="sxs-lookup"><span data-stu-id="23376-135">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="23376-136">Autoidentificadores en constructores</span><span class="sxs-lookup"><span data-stu-id="23376-136">Self Identifiers in Constructors</span></span>
<span data-ttu-id="23376-137">En otros miembros, proporcione un nombre para el objeto actual en la definición de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="23376-137">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="23376-138">También puede colocar el identificador propio en la primera línea de la definición de clase mediante el uso de la `as` palabra clave inmediatamente después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="23376-138">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="23376-139">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="23376-139">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="23376-140">En los constructores adicionales, también puede definir un identificador propio colocando el `as` cláusula justo después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="23376-140">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="23376-141">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="23376-141">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="23376-142">Pueden producirse problemas al intentar utilizar un objeto antes de definirla por completo.</span><span class="sxs-lookup"><span data-stu-id="23376-142">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="23376-143">Por lo tanto, los usos del propio identificador pueden causar el compilador emite una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicialice el objeto.</span><span class="sxs-lookup"><span data-stu-id="23376-143">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="23376-144">Sólo se debe utilizar el identificador propio en el `do` enlaces del constructor primario o después de la `then` palabra clave en los constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="23376-144">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="23376-145">El nombre del propio identificador no tiene que ser `this`.</span><span class="sxs-lookup"><span data-stu-id="23376-145">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="23376-146">Puede ser cualquier identificador válido.</span><span class="sxs-lookup"><span data-stu-id="23376-146">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="23376-147">Asignar valores a propiedades en la inicialización</span><span class="sxs-lookup"><span data-stu-id="23376-147">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="23376-148">Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización mediante la anexión de una lista de asignaciones del formulario `property = value` a la lista de argumentos para un constructor.</span><span class="sxs-lookup"><span data-stu-id="23376-148">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="23376-149">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="23376-149">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="23376-150">La versión siguiente del código anterior muestra la combinación de argumentos ordinarios, argumentos opcionales y configuración de propiedades de una llamada de constructor.</span><span class="sxs-lookup"><span data-stu-id="23376-150">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="23376-151">Constructores de clase heredada</span><span class="sxs-lookup"><span data-stu-id="23376-151">Constructors in inherited class</span></span>
<span data-ttu-id="23376-152">Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula de heredar.</span><span class="sxs-lookup"><span data-stu-id="23376-152">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="23376-153">Para obtener más información, consulte [constructores y herencia](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="23376-153">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="23376-154">Constructores estáticos o constructores de tipo</span><span class="sxs-lookup"><span data-stu-id="23376-154">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="23376-155">Además de especificar código para crear objetos, estáticos `let` y `do` enlaces se pueden crear en tipos de clase que se ejecutan antes de que el tipo en primer lugar se utiliza para realizar la inicialización en el nivel de tipo.</span><span class="sxs-lookup"><span data-stu-id="23376-155">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="23376-156">Para obtener más información, consulte [ `let` enlaces en clases](let-bindings-in-classes.md) y [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="23376-156">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23376-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="23376-157">See Also</span></span>
[<span data-ttu-id="23376-158">Miembros</span><span class="sxs-lookup"><span data-stu-id="23376-158">Members</span></span>](index.md)