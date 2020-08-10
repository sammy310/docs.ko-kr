---
title: COM interop 프로그래밍에서 인덱싱된 속성을 사용하는 방법 - C# 프로그래밍 가이드
description: 이 C# 예제에서 어떻게 인덱싱된 속성이 매개 변수가 있는 COM 속성이 사용되는 방식을 개선하는지 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: abd785864bd79d455024cb4501c76a21b349aa91
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303012"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="7daeb-103">COM interop 프로그래밍에서 인덱싱된 속성을 사용하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7daeb-103">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>
<span data-ttu-id="7daeb-104">*인덱싱된 속성*은 매개 변수가 있는 COM 속성이 C# 프로그래밍에서 사용되는 방식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-104">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="7daeb-105">인덱싱된 속성은 Visual C#의 다른 기능(예: [명명된 인수 및 선택적 인수](../classes-and-structs/named-and-optional-arguments.md)), 새 형식([dynamic](../../language-reference/builtin-types/reference-types.md)), [포함된 형식 정보](../../../standard/assembly/embed-types-visual-studio.md)와 함께 작동하여 Microsoft Office 프로그래밍을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-105">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="7daeb-106">이전 버전의 C#에서는 `get` 메서드에 매개 변수가 없고 `set` 메서드에 하나의 값 매개 변수가 있는 경우에만 메서드를 속성으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-106">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="7daeb-107">그러나 모든 COM 속성이 이러한 제한을 충족하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-107">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="7daeb-108">예를 들어 Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> 속성에는 범위 이름에 대한 매개 변수가 필요한 `get` 접근자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-108">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="7daeb-109">이전에는 `Range` 속성에 직접 액세스할 수 없었기 때문에 다음 예제와 같이 `get_Range` 메서드를 대신 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-109">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="7daeb-110">인덱싱된 속성을 사용하면 대신 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-110">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="7daeb-111">또한 앞의 예제에서는 [선택적 인수](../classes-and-structs/named-and-optional-arguments.md) 기능을 사용하므로 `Type.Missing`을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-111">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="7daeb-112">마찬가지로, C# 3.0 이하에서 <xref:Microsoft.Office.Interop.Excel.Range> 개체의 `Value` 속성 값을 설정하려면 두 개의 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-112">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="7daeb-113">하나는 범위 값의 형식을 지정하는 선택적 매개 변수의 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-113">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="7daeb-114">다른 하나는 `Value` 속성의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-114">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="7daeb-115">다음 예제에서는 이러한 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-115">The following examples illustrate these techniques.</span></span> <span data-ttu-id="7daeb-116">둘 다 A1 셀의 값을 `Name`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-116">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="7daeb-117">인덱싱된 속성을 사용하면 대신 다음 코드와 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-117">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="7daeb-118">인덱싱된 속성을 직접 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-118">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="7daeb-119">이 기능은 기존 인덱싱된 속성의 사용만을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-119">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7daeb-120">예제</span><span class="sxs-lookup"><span data-stu-id="7daeb-120">Example</span></span>  
 <span data-ttu-id="7daeb-121">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7daeb-121">The following code shows a complete example.</span></span> <span data-ttu-id="7daeb-122">Office API에 액세스하는 프로젝트를 설정하는 방법에 대한 자세한 내용은 [Visual C# 기능을 사용하여 Office interop 개체에 액세스하는 방법](./how-to-access-office-onterop-objects.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7daeb-122">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7daeb-123">참조</span><span class="sxs-lookup"><span data-stu-id="7daeb-123">See also</span></span>

- [<span data-ttu-id="7daeb-124">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="7daeb-124">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="7daeb-125">dynamic</span><span class="sxs-lookup"><span data-stu-id="7daeb-125">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="7daeb-126">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="7daeb-126">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="7daeb-127">Office 프로그래밍에 명명된 인수와 선택적 인수 사용 방법</span><span class="sxs-lookup"><span data-stu-id="7daeb-127">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="7daeb-128">C# 기능을 사용하여 Office interop 개체에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="7daeb-128">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="7daeb-129">연습: Office 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7daeb-129">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
