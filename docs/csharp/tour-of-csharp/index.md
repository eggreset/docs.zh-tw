---
title: "C# 的教學課程 | C# 指南"
description: "第一次接觸 C#？ 了解該語言的基本概念。"
keywords: .NET, .NET Core, C#, C# Primer, C# Guide
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: ebc727cd-8112-42e7-b59c-3c2873ad661c
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7249f1bed4395671cc294d5db83e83844782736a
ms.lasthandoff: 03/13/2017

---

# <a name="a-tour-of-the-c-language"></a>C# 語言教學課程  

C# (唸成 “See Sharp”) 是簡單、現代、物件導向且型別安全的程式設計語言。 C# 源自於是 C 系列語言，使用 C、C++、Java 和 JavaScript 的程式設計人員會立即感到熟悉。

C# 是物件導向的語言，但 C# 更進一步支援「元件導向」程式設計。 現代軟體設計逐漸依賴功能性上獨立與屬於自我描述套件的軟體元件。 這類元件的關鍵在於它們呈現含有屬性、方法和事件的程式設計模型；它們提供元件相關宣告資訊的屬性，且併入自己的文件。 C# 提供語言建構來直接支援這些概念，使 C# 成為對建立及使用軟體元件都非常自然的語言。

以下幾個 C# 功能有助於建構健全且持久的應用程式：「記憶體回收」自動取回不可能執行到且未使用的物件所佔用的記憶體；「例外狀況處理」針對錯誤偵測及復原提供結構化且可延伸的方法；該語言「型別安全」的設計使讀取未初始化的變數、索引超出陣列的範圍，或執行未檢查的型別轉換變得不可能。

C# 有***統一的型別系統***。 所有的 C# 型別 (包括 `int` 和 `double` 等基本型別) 都繼承自單一的 `object` 根型別。 因此，所有型別都擁有相同的一組常見作業，且任何型別的值都能以相同方式儲存、傳送及操作。 此外，C# 支援使用者定義的參考型別和數值型別，因此能動態配置物件，以及內嵌儲存輕量結構。

為了確保 C# 程式和程式庫能以相容的方式隨時間演進，C# 的設計中特別強調「版本控制」。 許多程式設計語言並不注重此問題，因此當推出新版的相依程式庫時，以那些語言撰寫的程式需要進行較多修改才能繼續運作。 直接受版本控制考量影響的 C# 設計層面包括個別的 `virtual` 與 `override` 修飾詞、方法多載解析的規則，以及對明確介面成員宣告的支援。

## <a name="hello-world"></a>Hello World

“Hello, World” 程式通常用來介紹某個程式設計語言。 以下是以 C# 撰寫的：

[!code-csharp[Hello World](../../../samples/snippets/csharp/tour/hello/Program.cs#L1-L8)]

C# 原始程式檔的副檔名通常是 `.cs`。 假設 “Hello, World” 程式儲存在 `hello.cs` 檔案中，該程式可以使用命令列編譯：

```console
csc hello.cs
```

這樣會建立名稱為 hello.exe 的可執行組件。 當此應用程式執行時，它產生的輸出為：

```console
Hello, World
```

> [!IMPORTANT]
> `csc` 命令會針對完整架構進行編譯，而且可能不是在所有平台上都能取得。


“Hello, World” 程式的開頭是參考 `System` 命名空間的 `using` 指示詞。 命名空間提供組織 C# 程式和程式庫的階層式方法。 命名空間包含型別和其他命名空間，例如 `System` 命名空間包含數個型別 (如程式中參考的 `Console` 類別)，和數個其他命名空間 (如 `IO` 和 `Collections`)。 使用 `using` 指示詞參考指定的命名空間，就能以非限定的方式使用屬於該命名空間成員的型別。 因為 `using` 指示詞的緣故，該程式可以使用 `Console.WriteLine` 當作 `System.Console.WriteLine` 的縮寫。

“Hello, World” 程式宣告的 `Hello` 類別具有單一成員 (名稱為 `Main` 的方法)。 `Main` 方法是使用 static 修飾詞來宣告。 執行個體方法可以使用關鍵字 `this` 參考特定的封入物件執行個體，但靜態方法卻不需要參考特定物件即可運作。 依照慣例，會使用名為 `Main` 的靜態方法做為程式的進入點。

程式的輸出是由 `System` 命名空間中 `Console` 類別的 `WriteLine` 方法產生。 此類別是由標準類別程式庫提供，根據預設，編譯器會自動參考此程式庫。

C# 還有更多可探討的主題。  下列主題提供 C# 語言元素的概觀。 這些概觀提供此語言所有元素的基本資訊，並且提供您深入了解 C# 語言元素的必要資訊：

* [程式結構](program-structure.md)
    - 了解 C# 語言的重要組織概念：***程式***、***命名空間***、***型別***、***成員***和***組件***。
* [類型與變數](types-and-variables.md)
    - 了解 C# 語言中的***實值型別***、***參考型別***和***變數***。
* [運算式](expressions.md)
    - 「運算式」是由「運算元」和「運算子」建構而成。 運算式會產生值。
* [陳述式](statements.md)
    - 您會使用***陳述式***來表達程式的動作。
* [類別與物件](classes-and-objects.md)
    - ***類別***是 C# 最基本的型別。 ***物件***是類別的執行個體。 類別是使用***成員*** (此主題中也有探討) 來建置。
* [結構](structs.md)
    - 不同於類別，***結構***是屬於實值型別的資料結構。
* [陣列](arrays.md)
    - ***陣列***是一種資料結構，其中包含一些可透過計算索引存取的變數。
* [介面](interfaces.md)
    - 「介面」定義可由類別和結構實作的合約。 介面可以包含方法、屬性、事件和索引子。 介面不提供它所定義之成員的實作 (它只會指定必須由類別提供的成員或實作介面的結構)。
* [列舉](enums.md)
    - 「列舉型別」是含一組具名常數的相異實值型別。
* [委派](delegates.md)
    - 「委派型別」代表對方法的參考，其中含有特定參數清單與傳回型別。 委派讓您可將方法視為實體，而實體能指派給變數或當作參數來傳遞。 委派就類似其他程式設計語言中的函式指標，但與函式指標的不同之處是，委派是物件導向且為型別安全。
* [屬性](attributes.md)
     * ***屬性***讓程式能指定型別、成員與實體的相關額外宣告資訊。

>[!div class="step-by-step"]
[下一步](program-structure.md)
