---
title: Estructuras (F#)
description: "Obtenga información acerca de la estructura de F #, un tipo de objeto compact a menudo más eficaz que una clase para los tipos con una pequeña cantidad de datos y un comportamiento simple."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="54a35-104">Estructuras</span><span class="sxs-lookup"><span data-stu-id="54a35-104">Structures</span></span>

<span data-ttu-id="54a35-105">A *estructura* es un tipo de objeto compacto que puede ser más eficaz que una clase para tipos que tienen una pequeña cantidad de datos y un comportamiento simple.</span><span class="sxs-lookup"><span data-stu-id="54a35-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="54a35-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54a35-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="54a35-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54a35-107">Remarks</span></span>
<span data-ttu-id="54a35-108">Las estructuras son *los tipos de valor*, lo que significa que se almacenan directamente en la pila o, cuando se usan como campos o elementos de matriz, en línea en el elemento primario del tipo.</span><span class="sxs-lookup"><span data-stu-id="54a35-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="54a35-109">A diferencia de los registros y las clases, las estructuras tienen semántica de paso por valor.</span><span class="sxs-lookup"><span data-stu-id="54a35-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="54a35-110">Esto significa que son útiles principalmente para pequeños agregados de datos a los que accede y que se copian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="54a35-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="54a35-111">En la sintaxis anterior, se muestran dos formularios.</span><span class="sxs-lookup"><span data-stu-id="54a35-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="54a35-112">La primera no es la sintaxis ligera; sin embargo, se utiliza frecuentemente porque, cuando se usan las palabras clave `struct` y `end`, se puede omitir el atributo `StructAttribute`, que aparece en el segundo formulario.</span><span class="sxs-lookup"><span data-stu-id="54a35-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="54a35-113">`StructAttribute` se puede abreviar como `Struct`.</span><span class="sxs-lookup"><span data-stu-id="54a35-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="54a35-114">El *elementos de definición de tipo* en la sintaxis anterior representa definiciones y declaraciones de miembros.</span><span class="sxs-lookup"><span data-stu-id="54a35-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="54a35-115">Las estructuras pueden tener constructores y campos mutables e inmutables, y pueden declarar implementaciones de interfaces y miembros.</span><span class="sxs-lookup"><span data-stu-id="54a35-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="54a35-116">Para obtener más información, consulte [miembros](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="54a35-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="54a35-117">Las estructuras no pueden participar en la herencia, no pueden contener enlaces `let` ni `do`, y no puede contener de forma recursiva campos de su propio tipo (aunque pueden contener celdas de referencia que hagan referencia a su propio tipo).</span><span class="sxs-lookup"><span data-stu-id="54a35-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="54a35-118">Dado que las estructuras no permiten enlaces `let`, debe declarar campos en estructuras mediante el uso de la palabra clave `val`.</span><span class="sxs-lookup"><span data-stu-id="54a35-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="54a35-119">La palabra clave `val` define un campo y su tipo, pero no permite la inicialización.</span><span class="sxs-lookup"><span data-stu-id="54a35-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="54a35-120">En su lugar, las declaraciones `val` se inicializan en cero o null.</span><span class="sxs-lookup"><span data-stu-id="54a35-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="54a35-121">Por este motivo, las estructuras que tienen un constructor implícito (es decir, los parámetros que se proporcionan inmediatamente después del nombre de la estructura en la declaración) requieren que las declaraciones `val` se anoten con el atributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="54a35-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="54a35-122">Las estructuras que tienen un constructor definido todavía admiten la inicialización en cero.</span><span class="sxs-lookup"><span data-stu-id="54a35-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="54a35-123">Por lo tanto, el atributo `DefaultValue` es una declaración de que ese valor cero es válido para el campo.</span><span class="sxs-lookup"><span data-stu-id="54a35-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="54a35-124">Los constructores implícitos de las estructuras no realizan ninguna acción porque los enlaces `let` y `do` no están permitidos en el tipo, pero los valores de parámetro de constructor implícito pasados están disponibles como campos privados.</span><span class="sxs-lookup"><span data-stu-id="54a35-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="54a35-125">Los constructores explícitos podrían implicar la inicialización de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="54a35-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="54a35-126">Cuando se tiene una estructura con un constructor explícito, se admite la inicialización en cero; sin embargo, no se utiliza el atributo `DefaultValue` en las declaraciones `val` porque entra en conflicto con el constructor explícito.</span><span class="sxs-lookup"><span data-stu-id="54a35-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="54a35-127">Para obtener más información acerca de `val` declaraciones, vea [campos explícitos: el `val` palabra clave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="54a35-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="54a35-128">Los atributos y modificadores de accesibilidad están permitidos en las estructuras y siguen las mismas reglas que las de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="54a35-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="54a35-129">Para obtener más información, consulte [atributos](attributes.md) y [el Control de acceso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="54a35-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="54a35-130">Los siguientes ejemplos de código ilustran las definiciones de la estructura.</span><span class="sxs-lookup"><span data-stu-id="54a35-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="54a35-131">Struct registros y uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="54a35-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="54a35-132">A partir de F # 4.1, puede representar [registros](records.md) y [uniones discriminadas](discriminated-unions.md) como estructuras con el `[<Struct>]` atributo.</span><span class="sxs-lookup"><span data-stu-id="54a35-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="54a35-133">Vea cada artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54a35-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54a35-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="54a35-134">See Also</span></span>
[<span data-ttu-id="54a35-135">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="54a35-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="54a35-136">Clases</span><span class="sxs-lookup"><span data-stu-id="54a35-136">Classes</span></span>](classes.md)

[<span data-ttu-id="54a35-137">Registros</span><span class="sxs-lookup"><span data-stu-id="54a35-137">Records</span></span>](records.md)

[<span data-ttu-id="54a35-138">Miembros</span><span class="sxs-lookup"><span data-stu-id="54a35-138">Members</span></span>](members/index.md)