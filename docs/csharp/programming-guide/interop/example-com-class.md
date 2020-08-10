---
title: COM 클래스 예제 - C# 프로그래밍 가이드
description: C#에서 클래스를 COM 개체로 노출하는 방법을 알아봅니다. 이 예제에서는 .cs 파일의 코드를 프로젝트에 추가하고 COM Interop 등록 속성을 설정합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: 4ea66ba26595c5bae2e579d1cc85c4b0d58616df
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303038"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="c84f0-104">COM 클래스 예제(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c84f0-104">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="c84f0-105">다음은 COM 개체로 노출되는 클래스의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-105">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="c84f0-106">이 코드를 .cs 파일에 배치하고 프로젝트에 추가한 후 **COM Interop 등록** 속성을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-106">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="c84f0-107">자세한 내용은 [방법: COM Interop에 대한 구성 요소 등록](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c84f0-107">For more information, see [How to: Register a Component for COM Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span></span>
  
 <span data-ttu-id="c84f0-108">Visual C# 개체를 COM에 노출하려면 클래스 인터페이스, 필요한 경우 이벤트 인터페이스 및 클래스 자체를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-108">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="c84f0-109">클래스 멤버가 COM에 표시되려면 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-109">Class members must follow these rules to be visible to COM:</span></span>  
  
- <span data-ttu-id="c84f0-110">클래스는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-110">The class must be public.</span></span>  
  
- <span data-ttu-id="c84f0-111">속성, 메서드 및 이벤트는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-111">Properties, methods, and events must be public.</span></span>  
  
- <span data-ttu-id="c84f0-112">속성 및 메서드는 클래스 인터페이스에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-112">Properties and methods must be declared on the class interface.</span></span>  
  
- <span data-ttu-id="c84f0-113">이벤트는 이벤트 인터페이스에서 선언되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-113">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="c84f0-114">이러한 인터페이스에 선언되지 않은 클래스의 다른 public 멤버는 COM에 표시되지 않지만 다른 .NET 개체에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-114">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET objects.</span></span>  
  
 <span data-ttu-id="c84f0-115">속성 및 메서드를 COM에 노출하려면 클래스 인터페이스에서 선언하고 `DispId` 특성을 사용하여 표시한 후 클래스에서 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-115">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="c84f0-116">멤버가 인터페이스에서 선언되는 순서는 COM vtable에 사용되는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-116">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="c84f0-117">클래스에서 이벤트를 노출하려면 이벤트 인터페이스에서 선언하고 `DispId` 특성을 사용하여 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-117">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="c84f0-118">클래스는 이 인터페이스를 구현하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-118">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="c84f0-119">클래스는 클래스 인터페이스를 구현합니다. 둘 이상의 인터페이스를 구현할 수 있지만 첫 번째 구현이 기본 클래스 인터페이스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-119">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="c84f0-120">여기에서 COM에 노출된 메서드 및 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-120">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="c84f0-121">이러한 메서드 및 속성은 public으로 표시되어야 하며 클래스 인터페이스의 선언과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-121">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="c84f0-122">또한 여기에서 클래스에 의해 발생된 이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-122">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="c84f0-123">이러한 이벤트는 public으로 표시되어야 하며 이벤트 인터페이스의 선언과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c84f0-123">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84f0-124">예제</span><span class="sxs-lookup"><span data-stu-id="c84f0-124">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="c84f0-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c84f0-125">See also</span></span>

- [<span data-ttu-id="c84f0-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c84f0-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c84f0-127">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="c84f0-127">Interoperability</span></span>](./index.md)
- [<span data-ttu-id="c84f0-128">프로젝트 디자이너, 빌드 페이지(C#)</span><span class="sxs-lookup"><span data-stu-id="c84f0-128">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
