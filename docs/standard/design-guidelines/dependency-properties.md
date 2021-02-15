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
# <a name="dependency-properties"></a>종속성 속성

DP(종속성 속성)는 해당 값을 형식 변수(필드)에 저장하는 대신 속성 저장소에 저장하는 일반 속성입니다.

 연결된 종속성 속성은 개체와 해당 컨테이너 간의 관계(예: `Panel` 컨테이너에서 `Button` 개체의 위치)를 설명하는 “속성”을 나타내는 정적 Get 및 Set 메서드로 모델링된 일종의 종속성 속성입니다.

 ✔️ 스타일 지정, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스, 상속 등 WPF 기능을 지원하는 속성이 필요한 경우 종속성 속성을 제공하세요.

## <a name="dependency-property-design"></a>종속성 속성 디자인

 ✔️ 종속성 속성을 구현할 때는 <xref:System.Windows.DependencyObject> 또는 해당 하위 형식 중 하나에서 상속하세요. 형식은 속성 저장소의 매우 효율적인 구현을 제공하며 WPF 데이터 바인딩을 자동으로 지원합니다.

 ✔️ 일반 CLR 속성 및 각 종속성 속성에 대해 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType>의 인스턴스를 저장하는 퍼블릭 정적 읽기 전용 필드를 제공하세요.

 ✔️ 인스턴스 메서드 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 및 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>를 호출하여 종속성 속성을 구현하세요.

 ✔️ 속성의 이름에 접미사 “Property”를 사용하여 종속성 속성 정적 필드의 이름을 지정하세요.

 ❌ 코드에서 종속성 속성의 기본값을 명시적으로 설정하지 마세요. 대신 메타데이터에서 설정하세요.

 속성 기본값을 명시적으로 설정하는 경우 스타일 지정과 같은 일부 암시적 방법으로 해당 속성을 설정하지 못할 수 있습니다.

 ❌ 정적 필드에 액세스하기 위해 표준 코드 이외의 코드를 속성 접근자에 배치하지 마세요.

 스타일 지정에서는 정적 필드를 직접 사용하기 때문에 속성이 스타일 지정과 같은 암시적 방법으로 설정된 경우 해당 코드가 실행되지 않습니다.

 ❌ 보안 데이터를 저장하는 데 종속성 속성을 사용하지 마세요. 프라이빗 종속성 속성도 공개적으로 액세스할 수 있습니다.

## <a name="attached-dependency-property-design"></a>연결된 종속성 속성 디자인

 이전 섹션에서 설명한 종속성 속성은 선언 형식의 기본 속성을 나타냅니다. 예를 들어 `Text` 속성은 이 속성을 선언하는 `TextButton`의 속성입니다. 특별한 종류의 종속성 속성은 연결된 종속성 속성입니다.

 연결된 속성의 전형적인 예로 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성이 있습니다. 이 속성은 그리드가 아닌 단추의 열 위치를 나타내지만 단추가 그리드에 포함된 경우에만 적용되므로 그리드에 의해 단추에 “연결”됩니다.

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

 연결된 속성의 정의는 접근자가 정적 Get 및 Set 메서드로 표시된다는 점을 제외하면 일반 종속성 속성의 정의와 거의 유사합니다.

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

## <a name="dependency-property-validation"></a>종속성 속성 유효성 검사

 속성은 종종 유효성 검사라는 기능을 구현합니다. 유효성 검사 논리는 속성의 값을 변경하려고 할 때 실행됩니다.

 아쉽게도 종속성 속성 접근자는 임의의 유효성 검사 코드를 포함할 수 없습니다. 대신 속성 등록 중에 종속성 속성 유효성 검사 논리를 지정해야 합니다.

 ❌ 속성의 접근자에 종속성 속성 유효성 검사 논리를 넣지 마세요. 대신 `DependencyProperty.Register` 메서드에 유효성 검사 콜백을 전달하세요.

## <a name="dependency-property-change-notifications"></a>종속성 속성 변경 알림

 ❌ 종속성 속성 접근자에서 변경 알림 논리를 구현하지 마세요. 종속성 속성에는 기본 제공 변경 알림 기능이 있으며, 이 기능을 사용하려면 <xref:System.Windows.PropertyMetadata>에 대한 변경 알림 콜백을 제공해야 합니다.

## <a name="dependency-property-value-coercion"></a>종속성 속성 값 강제 변환

 속성 저장소가 실제로 수정되기 전에 속성 setter에 지정된 값이 setter에 의해 수정되는 경우 속성 강제 변환이 수행됩니다.

 ❌ 종속성 속성 접근자에서 강제 변환 논리를 구현하지 마세요.

 종속성 속성에는 기본 제공 강제 변환 기능이 있으며 이 기능은 `PropertyMetadata`에 대한 강제 변환 콜백을 제공하여 사용할 수 있습니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [일반 디자인 패턴](common-design-patterns.md)
