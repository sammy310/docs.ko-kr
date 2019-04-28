---
title: 종속성 속성
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: 52d7a69a3f52c67ebff3f3db1daf0790e995913a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778770"
---
# <a name="dependency-properties"></a><span data-ttu-id="efb95-102">종속성 속성</span><span class="sxs-lookup"><span data-stu-id="efb95-102">Dependency Properties</span></span>
<span data-ttu-id="efb95-103">종속성 속성 (DP)에 예를 들어 형식 변수에 (필드)를 저장 하는 대신 속성 저장소에서 해당 값을 저장 하는 일반 속성이입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="efb95-104">연결 된 종속성 속성은 개체와 해당 컨테이너 간의 관계를 설명 하는 "속성"을 나타내는 정적 Get 및 Set 메서드를 모델링 하는 종속성 속성의 종류 (예를 들어 위치는 `Button` 에서 개체를 `Panel` 컨테이너)입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="efb95-105">**✓ DO** 스타일 지정, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스 상속 같은 WPF 기능을 지 원하는 속성을 사용 해야 할 경우 종속성 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="efb95-106">종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="efb95-106">Dependency Property Design</span></span>  
 <span data-ttu-id="efb95-107">**✓ DO** 에서 상속 <xref:System.Windows.DependencyObject>, 또는 종속성 속성을 구현 하는 경우 하위 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="efb95-108">형식 속성 저장소의 매우 효과적인 구현을 제공 하 고 자동으로 WPF 데이터 바인딩을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="efb95-109">**✓ DO** 일반 CLR 속성 및 인스턴스를 저장 합니다. 공용 정적 읽기 전용 필드를 제공 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> 각 종속성 속성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="efb95-110">**✓ DO** 인스턴스 메서드를 호출 하 여 종속성 속성을 구현 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 및 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="efb95-111">**✓ DO** "속성과" 속성의 이름을 접미사로 붙여 하 여 종속성 속성의 정적 필드의 이름을</span><span class="sxs-lookup"><span data-stu-id="efb95-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="efb95-112">**X DO NOT** 코드에서 종속성 속성의 기본값을 명시적으로 설정; 대신 메타 데이터에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="efb95-113">속성 기본값을 명시적으로 설정한 경우 일부 암시적 스타일을 같은 방법으로 설정 되 고 해당 속성을 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="efb95-114">**X DO NOT** 정적 필드에 액세스 하는 표준 코드 이외의 속성 접근자에 코드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="efb95-115">정적 필드를 직접 사용 스타일을 지정 하기 때문에 속성을 스타일 같은 암시적 방법으로 설정 된 경우 코드가 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="efb95-116">**X DO NOT** 종속성 속성을 사용 하 여 보안 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="efb95-117">비공개 종속성 속성은 공개적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="efb95-118">연결 된 종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="efb95-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="efb95-119">이전 섹션에서 설명 하는 종속성 속성 선언 형식의 기본 속성을 나타내는 예를 들어 합니다 `Text` 속성은 속성의 `TextButton`를 선언 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="efb95-120">종속성 속성에는 특수 한 유형의 연결 된 종속성 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="efb95-121">연결된 된 속성의 전형적인 예로 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="efb95-122">속성 단추 (없습니다 표) 열의 위치를 나타내지만 관련 되 고 "에 연결 되어" 단추 그리드에서 단추를 모눈에 포함 된 경우.</span><span class="sxs-lookup"><span data-stu-id="efb95-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```xaml
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="efb95-123">연결된 된 속성의 정의 같습니다. 대부분의 일반 종속성 속성을 제외 하 고 접근자는 정적 Get 및 Set 메서드를 통해 표시 됩니다</span><span class="sxs-lookup"><span data-stu-id="efb95-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```csharp
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="efb95-124">종속성 속성의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="efb95-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="efb95-125">속성은 종종 유효성 검사를 어떻게 지칭 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="efb95-126">속성의 값을 변경 하려고 시도 하는 경우 유효성 검사 논리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="efb95-127">그러나 종속성 속성 접근자는 임의의 유효성 검사 코드를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="efb95-128">대신 종속성 속성 유효성 검사 논리 속성을 등록할 때 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="efb95-129">**X DO NOT** 속성의 접근자에 종속성 속성 유효성 검사 논리를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="efb95-130">대신, 유효성 검사 콜백을 전달 `DependencyProperty.Register` 메서드.</span><span class="sxs-lookup"><span data-stu-id="efb95-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="efb95-131">종속성 속성 변경 알림</span><span class="sxs-lookup"><span data-stu-id="efb95-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="efb95-132">**X DO NOT** 종속성 속성 접근자의 변경 알림 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="efb95-133">종속성 속성에 대 한 변경 알림 콜백을 제공 하 여 사용 해야 하는 기본 제공 변경 알림 기능에는 <xref:System.Windows.PropertyMetadata>합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="efb95-134">종속성 속성 값 강제 변환</span><span class="sxs-lookup"><span data-stu-id="efb95-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="efb95-135">속성의 강제 변환을 속성 저장소를 실제로 수정 하기 전에 속성 setter에 지정 된 값이 setter에서 수정 될 때 수행이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="efb95-136">**X DO NOT** 종속성 속성 접근자에서 강제 변환 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="efb95-137">종속성 속성 기능이 기본 제공 강제 변환이 및 강제 변환 콜백을 제공 하 여 사용할 수는 `PropertyMetadata`합니다.</span><span class="sxs-lookup"><span data-stu-id="efb95-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="efb95-138">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="efb95-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="efb95-139">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="efb95-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb95-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="efb95-140">See also</span></span>

- [<span data-ttu-id="efb95-141">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="efb95-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="efb95-142">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="efb95-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
