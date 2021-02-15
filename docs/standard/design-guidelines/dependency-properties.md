---
description: '자세한 정보: 종속성 속성'
title: 종속성 속성
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: 78b141d6e8d1bb6bd5cf050a89aa67705111bae3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642307"
---
# <a name="dependency-properties"></a><span data-ttu-id="3dc74-103">종속성 속성</span><span class="sxs-lookup"><span data-stu-id="3dc74-103">Dependency Properties</span></span>

<span data-ttu-id="3dc74-104">DP(종속성 속성)는 해당 값을 형식 변수(필드)에 저장하는 대신 속성 저장소에 저장하는 일반 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-104">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>

 <span data-ttu-id="3dc74-105">연결된 종속성 속성은 개체와 해당 컨테이너 간의 관계(예: `Panel` 컨테이너에서 `Button` 개체의 위치)를 설명하는 “속성”을 나타내는 정적 Get 및 Set 메서드로 모델링된 일종의 종속성 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-105">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>

 <span data-ttu-id="3dc74-106">✔️ 스타일 지정, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스, 상속 등 WPF 기능을 지원하는 속성이 필요한 경우 종속성 속성을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-106">✔️ DO provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>

## <a name="dependency-property-design"></a><span data-ttu-id="3dc74-107">종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="3dc74-107">Dependency Property Design</span></span>

 <span data-ttu-id="3dc74-108">✔️ 종속성 속성을 구현할 때는 <xref:System.Windows.DependencyObject> 또는 해당 하위 형식 중 하나에서 상속하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-108">✔️ DO inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="3dc74-109">형식은 속성 저장소의 매우 효율적인 구현을 제공하며 WPF 데이터 바인딩을 자동으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-109">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>

 <span data-ttu-id="3dc74-110">✔️ 일반 CLR 속성 및 각 종속성 속성에 대해 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType>의 인스턴스를 저장하는 퍼블릭 정적 읽기 전용 필드를 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-110">✔️ DO provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>

 <span data-ttu-id="3dc74-111">✔️ 인스턴스 메서드 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 및 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>를 호출하여 종속성 속성을 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-111">✔️ DO implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="3dc74-112">✔️ 속성의 이름에 접미사 “Property”를 사용하여 종속성 속성 정적 필드의 이름을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-112">✔️ DO name the dependency property static field by suffixing the name of the property with "Property."</span></span>

 <span data-ttu-id="3dc74-113">❌ 코드에서 종속성 속성의 기본값을 명시적으로 설정하지 마세요. 대신 메타데이터에서 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-113">❌ DO NOT set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>

 <span data-ttu-id="3dc74-114">속성 기본값을 명시적으로 설정하는 경우 스타일 지정과 같은 일부 암시적 방법으로 해당 속성을 설정하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-114">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>

 <span data-ttu-id="3dc74-115">❌ 정적 필드에 액세스하기 위해 표준 코드 이외의 코드를 속성 접근자에 배치하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-115">❌ DO NOT put code in the property accessors other than the standard code to access the static field.</span></span>

 <span data-ttu-id="3dc74-116">스타일 지정에서는 정적 필드를 직접 사용하기 때문에 속성이 스타일 지정과 같은 암시적 방법으로 설정된 경우 해당 코드가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-116">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>

 <span data-ttu-id="3dc74-117">❌ 보안 데이터를 저장하는 데 종속성 속성을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-117">❌ DO NOT use dependency properties to store secure data.</span></span> <span data-ttu-id="3dc74-118">프라이빗 종속성 속성도 공개적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-118">Even private dependency properties can be accessed publicly.</span></span>

## <a name="attached-dependency-property-design"></a><span data-ttu-id="3dc74-119">연결된 종속성 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="3dc74-119">Attached Dependency Property Design</span></span>

 <span data-ttu-id="3dc74-120">이전 섹션에서 설명한 종속성 속성은 선언 형식의 기본 속성을 나타냅니다. 예를 들어 `Text` 속성은 이 속성을 선언하는 `TextButton`의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-120">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="3dc74-121">특별한 종류의 종속성 속성은 연결된 종속성 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-121">A special kind of dependency property is the attached dependency property.</span></span>

 <span data-ttu-id="3dc74-122">연결된 속성의 전형적인 예로 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-122">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="3dc74-123">이 속성은 그리드가 아닌 단추의 열 위치를 나타내지만 단추가 그리드에 포함된 경우에만 적용되므로 그리드에 의해 단추에 “연결”됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-123">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>

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

 <span data-ttu-id="3dc74-124">연결된 속성의 정의는 접근자가 정적 Get 및 Set 메서드로 표시된다는 점을 제외하면 일반 종속성 속성의 정의와 거의 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-124">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>

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

## <a name="dependency-property-validation"></a><span data-ttu-id="3dc74-125">종속성 속성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="3dc74-125">Dependency Property Validation</span></span>

 <span data-ttu-id="3dc74-126">속성은 종종 유효성 검사라는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-126">Properties often implement what is called validation.</span></span> <span data-ttu-id="3dc74-127">유효성 검사 논리는 속성의 값을 변경하려고 할 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-127">Validation logic executes when an attempt is made to change the value of a property.</span></span>

 <span data-ttu-id="3dc74-128">아쉽게도 종속성 속성 접근자는 임의의 유효성 검사 코드를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-128">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="3dc74-129">대신 속성 등록 중에 종속성 속성 유효성 검사 논리를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-129">Instead, dependency property validation logic needs to be specified during property registration.</span></span>

 <span data-ttu-id="3dc74-130">❌ 속성의 접근자에 종속성 속성 유효성 검사 논리를 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-130">❌ DO NOT put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="3dc74-131">대신 `DependencyProperty.Register` 메서드에 유효성 검사 콜백을 전달하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-131">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>

## <a name="dependency-property-change-notifications"></a><span data-ttu-id="3dc74-132">종속성 속성 변경 알림</span><span class="sxs-lookup"><span data-stu-id="3dc74-132">Dependency Property Change Notifications</span></span>

 <span data-ttu-id="3dc74-133">❌ 종속성 속성 접근자에서 변경 알림 논리를 구현하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-133">❌ DO NOT implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="3dc74-134">종속성 속성에는 기본 제공 변경 알림 기능이 있으며, 이 기능을 사용하려면 <xref:System.Windows.PropertyMetadata>에 대한 변경 알림 콜백을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-134">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>

## <a name="dependency-property-value-coercion"></a><span data-ttu-id="3dc74-135">종속성 속성 값 강제 변환</span><span class="sxs-lookup"><span data-stu-id="3dc74-135">Dependency Property Value Coercion</span></span>

 <span data-ttu-id="3dc74-136">속성 저장소가 실제로 수정되기 전에 속성 setter에 지정된 값이 setter에 의해 수정되는 경우 속성 강제 변환이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-136">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>

 <span data-ttu-id="3dc74-137">❌ 종속성 속성 접근자에서 강제 변환 논리를 구현하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc74-137">❌ DO NOT implement coercion logic in dependency property accessors.</span></span>

 <span data-ttu-id="3dc74-138">종속성 속성에는 기본 제공 강제 변환 기능이 있으며 이 기능은 `PropertyMetadata`에 대한 강제 변환 콜백을 제공하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc74-138">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>

 <span data-ttu-id="3dc74-139">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="3dc74-139">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3dc74-140">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3dc74-140">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3dc74-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dc74-141">See also</span></span>

- [<span data-ttu-id="3dc74-142">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="3dc74-142">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="3dc74-143">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="3dc74-143">Common Design Patterns</span></span>](common-design-patterns.md)
