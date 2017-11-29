---
title: "屬性 (F#)"
description: "了解 F # 屬性如何啟用要套用至程式設計建構的中繼資料。"
keywords: "Visual F#, F#, 函式程式設計"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a><span data-ttu-id="cfd8b-104">屬性</span><span class="sxs-lookup"><span data-stu-id="cfd8b-104">Attributes</span></span>

<span data-ttu-id="cfd8b-105">屬性會啟用要套用至程式設計建構的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-105">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfd8b-106">語法</span><span class="sxs-lookup"><span data-stu-id="cfd8b-106">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="cfd8b-107">備註</span><span class="sxs-lookup"><span data-stu-id="cfd8b-107">Remarks</span></span>

<span data-ttu-id="cfd8b-108">在先前的語法，*目標*是選擇性的而且如果有的話，指定程式實體的屬性會套用至類型。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-108">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="cfd8b-109">有效值*目標*會出現在本文件稍後的表格所示。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-109">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="cfd8b-110">*屬性名稱*（可能是命名空間限定） 名稱的有效屬性類型，或後置詞不參考`Attribute`，通常使用於屬性的型別名稱。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-110">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="cfd8b-111">例如，型別`ObsoleteAttribute`可以縮短到`Obsolete`在此內容中。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-111">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="cfd8b-112">*引數*屬性型別建構函式的引數。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-112">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="cfd8b-113">如果屬性有預設建構函式，可以省略引數清單和括號。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-113">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="cfd8b-114">屬性支援位置引數和具名引數。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-114">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="cfd8b-115">*位置引數*是以它們出現的順序中使用的引數。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-115">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="cfd8b-116">如果屬性有公用屬性，可以使用具名引數。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-116">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="cfd8b-117">您可以設定這些引數清單中使用下列語法。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-117">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="cfd8b-118">這類屬性的初始化可以依任何順序，但它們必須遵循下列任何位置的引數。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-118">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="cfd8b-119">下列是屬性的範例的使用位置引數和屬性初始設定。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-119">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="cfd8b-120">在此範例中，屬性是`DllImportAttribute`，這裡用於縮短形式。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-120">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="cfd8b-121">第一個引數是位置參數，而且第二個是屬性。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-121">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="cfd8b-122">屬性是.NET 程式設計建構，可讓物件稱為*屬性*與類型或其他程式元素相關聯。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-122">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="cfd8b-123">屬性所套用的程式項目稱為*屬性目標*。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-123">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="cfd8b-124">屬性通常會包含其目標的相關中繼資料。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-124">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="cfd8b-125">在此情況下，中繼資料可能會以外的欄位和成員類型有關的任何資料。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-125">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="cfd8b-126">F # 中的屬性可以套用至下列程式設計建構： 函式、 方法、 組件、 模組、 類型 （類別、 記錄、 結構、 介面、 委派、 列舉、 等位和等等）、 建構函式、 屬性、 欄位、 參數、型別參數，並傳回值。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-126">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="cfd8b-127">屬性不允許在`let`類別、 運算式或工作流程運算式內的繫結。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-127">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="cfd8b-128">一般而言，屬性宣告出現之前屬性目標的宣告。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-128">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="cfd8b-129">可以使用多個屬性宣告，在一起，如下。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-129">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="cfd8b-130">您可以使用.NET 反映，在執行階段查詢屬性。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-130">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="cfd8b-131">您可以個別宣告多個屬性，如同先前的程式碼範例中，或您可以宣告一組括號中如果您使用分號來分隔個別的屬性和建構函式，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-131">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="cfd8b-132">通常發生的屬性包括`Obsolete`適用於 COM 支援、 擁有權的程式碼中，與相關的屬性和屬性，指出是否可序列化型別屬性的屬性，屬性的安全性考量。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-132">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="cfd8b-133">下列範例示範如何使用`Obsolete`屬性。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-133">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="cfd8b-134">屬性目標`assembly`和`module`，您將屬性套用至最上層`do`組件中的繫結。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-134">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="cfd8b-135">您可以包含單字`assembly`或`module`在屬性宣告中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-135">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="cfd8b-136">如果您省略套用至屬性的屬性目標`do`繫結時，F # 編譯器會嘗試判斷適合該屬性的屬性目標。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-136">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="cfd8b-137">許多屬性的類別有類型的屬性`System.AttributeUsageAttribute`包含支援該屬性的可能目標的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-137">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="cfd8b-138">如果`System.AttributeUsageAttribute`表示屬性支援做為目標的函式，屬性會從要套用至程式的主要進入點。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="cfd8b-139">如果`System.AttributeUsageAttribute`表示屬性支援做為目標的組件，編譯器會採用要套用至組件的屬性。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-139">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="cfd8b-140">大部分的屬性不會套用至函式和組件，但在其中執行的情況下，屬性是要套用至程式的 main 函式。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-140">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="cfd8b-141">如果明確指定之屬性目標，則屬性會套用至指定的目標。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-141">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="cfd8b-142">雖然您通常不需要指定屬性明確地目標的有效值*目標*屬性中會顯示在下列資料表中，以及使用方式的範例。</span><span class="sxs-lookup"><span data-stu-id="cfd8b-142">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="cfd8b-143">屬性目標</span><span class="sxs-lookup"><span data-stu-id="cfd8b-143">Attribute target</span></span></td>
    <th><span data-ttu-id="cfd8b-144">範例</span><span class="sxs-lookup"><span data-stu-id="cfd8b-144">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-145">組件</span><span class="sxs-lookup"><span data-stu-id="cfd8b-145">assembly</span></span></td>
    <td><span data-ttu-id="cfd8b-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="cfd8b-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-147">return</span><span class="sxs-lookup"><span data-stu-id="cfd8b-147">return</span></span></td>
    <td><span data-ttu-id="cfd8b-148">' function1 可讓 x: [<return: Obsolete>] int = x + 1'</span><span class="sxs-lookup"><span data-stu-id="cfd8b-148">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-149">Field - 欄位</span><span class="sxs-lookup"><span data-stu-id="cfd8b-149">field</span></span></td>
    <td><span data-ttu-id="cfd8b-150">' [<field: DefaultValue>] val mutable x: int'</span><span class="sxs-lookup"><span data-stu-id="cfd8b-150">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-151">屬性</span><span class="sxs-lookup"><span data-stu-id="cfd8b-151">property</span></span></td>
    <td><span data-ttu-id="cfd8b-152">' [<property: Obsolete>] 這。MyProperty = x'</span><span class="sxs-lookup"><span data-stu-id="cfd8b-152">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-153">Param</span><span class="sxs-lookup"><span data-stu-id="cfd8b-153">param</span></span></td>
    <td><span data-ttu-id="cfd8b-154">' 成員這。MyMethod ([<param: Out>] x: ref<int>) = x: = 10'</span><span class="sxs-lookup"><span data-stu-id="cfd8b-154">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="cfd8b-155">類型</span><span class="sxs-lookup"><span data-stu-id="cfd8b-155">type</span></span></td>
    <td><span data-ttu-id="cfd8b-156">
        ```
        [<type: StructLayout(Sequential)>] 輸入 MyStruct = struct x： 位元組 y: int 結束```
    </span><span class="sxs-lookup"><span data-stu-id="cfd8b-156">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="cfd8b-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cfd8b-157">See Also</span></span>

[<span data-ttu-id="cfd8b-158">F# 語言參考</span><span class="sxs-lookup"><span data-stu-id="cfd8b-158">F# Language Reference</span></span>](index.md)