---
title: x:Subclass 지시문
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: 850fe8acf9e47149bd385e78b30e04ba77d7a8b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140792"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="aaba8-102">x:Subclass 지시문</span><span class="sxs-lookup"><span data-stu-id="aaba8-102">x:Subclass Directive</span></span>
<span data-ttu-id="aaba8-103">XAML 태그 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="aaba8-104">기반이 되는 partial 클래스를 만드는 대신 `x:Class`에 제공 된 `x:Class` 중간 클래스로 만들어집니다 다음 제공 된 파생된 클래스는 기반으로 해야 하 고 `x:Class`입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="aaba8-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="aaba8-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="aaba8-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="aaba8-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`namespace`|<span data-ttu-id="aaba8-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-107">Optional.</span></span> <span data-ttu-id="aaba8-108">포함 된 CLR 네임 스페이스를 지정 `classname`합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="aaba8-109">하는 경우 `namespace` 지정 된 경우 점 (.) `namespace` 고 `classname`입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|  
|`classname`|<span data-ttu-id="aaba8-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aaba8-110">Required.</span></span> <span data-ttu-id="aaba8-111">로드 된 XAML 및 코드 숨김에는 XAML에 대 한 연결 하는 partial 클래스의 CLR 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="aaba8-112">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaba8-112">See Remarks.</span></span>|  
|`subclassNamespace`|<span data-ttu-id="aaba8-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-113">Optional.</span></span> <span data-ttu-id="aaba8-114">다를 수 있습니다 `namespace` 각 네임 스페이스는 다른 확인할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="aaba8-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="aaba8-115">포함 된 CLR 네임 스페이스를 지정 `subclassName`합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="aaba8-116">하는 경우 `subclassName` 지정 된 경우 점 (.) `subclassNamespace` 고 `subclassName`입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|  
|`subclassName`|<span data-ttu-id="aaba8-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aaba8-117">Required.</span></span> <span data-ttu-id="aaba8-118">서브 클래스의 CLR 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-118">Specifies the CLR name of the subclass.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="aaba8-119">종속성</span><span class="sxs-lookup"><span data-stu-id="aaba8-119">Dependencies</span></span>  
 <span data-ttu-id="aaba8-120">[X:class 지시문](x-class-directive.md) 동일한 개체에도 제공 해야 하며 해당 개체에는 XAML 프로덕션의 루트 요소 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-120">[x:Class Directive](x-class-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaba8-121">설명</span><span class="sxs-lookup"><span data-stu-id="aaba8-121">Remarks</span></span>  
 `x:Subclass` <span data-ttu-id="aaba8-122">사용량은 주로 partial 클래스 선언을 지원 하지 않는 언어에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-122">usage is primarily intended for languages that do not support partial class declarations.</span></span>  
  
 <span data-ttu-id="aaba8-123">로 사용 되는 클래스를 `x:Subclass` 중첩된 클래스일 수 없습니다. 및 `x:Subclass` "Dependencies" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>  
  
 <span data-ttu-id="aaba8-124">그렇지 않으면의 의미를 개념적 `x:Subclass` .NET Framework XAML 서비스 구현에서 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET Framework XAML Services implementation.</span></span> <span data-ttu-id="aaba8-125">즉,.NET Framework XAML 서비스 동작에는 XAML에서 태그 및 코드를 지 원하는 연결 된 전체 프로그래밍 모델을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-125">This is because .NET Framework XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="aaba8-126">관련 된 추가 개념 구현 `x:Class` 고 `x:Subclass` 프로그래밍 모델이 나 응용 프로그램 모델을 사용 하 여 XAML 태그, 컴파일된 태그 및 코드 숨김 CLR 기반 연결 하는 방법을 정의 하는 특정 프레임 워크에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="aaba8-127">각 프레임 워크 동작 또는 빌드 환경에 포함 되어야 하는 특정 구성 요소 중 일부를 사용 하도록 설정 하는 자체 빌드 작업이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="aaba8-128">프레임 워크 내에서 빌드 작업은 코드 숨김에 사용 되는 특정 CLR 언어에 따라 달라질 수도 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="aaba8-129">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="aaba8-129">WPF Usage Notes</span></span>  
 `x:Subclass` <span data-ttu-id="aaba8-130">페이지 루트 또는 수를 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의 루트 `x:Class`입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-130">can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="aaba8-131">선언 `x:Subclass` 페이지나 응용 프로그램 루트를 또는 없는 위치에서 지정 이외의 모든 요소에 대해 `x:Class` 존재 하 고 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>  
  
 <span data-ttu-id="aaba8-132">파생 클래스를 만드는 올바르게 동작 하는 `x:Subclass` 시나리오는 상당히 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="aaba8-133">중간 파일 (.xaml 파일 이름을 통합 하는 이름의 태그 컴파일에서 프로젝트의 obj 폴더에 생성 된.g 파일)을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="aaba8-134">이러한 중간 파일 컴파일된 응용 프로그램의 결합된 된 partial 클래스에서 특정 프로그래밍 구문의 출처를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>  
  
 <span data-ttu-id="aaba8-135">파생된 클래스에서 이벤트 처리기 여야 `internal override` (`Friend Overrides` Microsoft Visual Basic) 컴파일 중에 중간 클래스에서 생성 하는 대로 처리기에 대 한 스텁을 재정의 하려면.</span><span class="sxs-lookup"><span data-stu-id="aaba8-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="aaba8-136">그렇지 않으면 파생된 클래스 구현 (그림자) 중간 클래스 구현을 숨기고 중간 클래스 처리기가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>  
  
 <span data-ttu-id="aaba8-137">모두 정의 하는 경우 `x:Class` 하 고 `x:Subclass`를 참조 하는 클래스에 대 한 모든 구현을 제공할 필요가 없습니다 `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="aaba8-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="aaba8-138">통해 이름을 지정 해야 하는 `x:Class` 특성 컴파일러에 중간 파일 (이 컴파일러는 기본 이름이 선택 하지)에 생성 되는 클래스에 대 한 몇 가지 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="aaba8-139">그러나 제공할 수 있습니다 합니다 `x:Class` 클래스는 구현에 아닙니다 모두 사용 하 여 일반적인 시나리오 `x:Class` 및 `x:Subclass`합니다.</span><span class="sxs-lookup"><span data-stu-id="aaba8-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaba8-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="aaba8-140">See also</span></span>

- [<span data-ttu-id="aaba8-141">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="aaba8-141">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="aaba8-142">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="aaba8-142">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
