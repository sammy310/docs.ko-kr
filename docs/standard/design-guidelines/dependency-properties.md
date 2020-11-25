---
title: 종속성 속성
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: ab30da59670c146874defe86b1d048f97eebf449
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734766"
---
# <a name="dependency-properties"></a>종속성 속성

DP (종속성 속성)는 형식 변수 (필드)에 저장 하는 대신 속성 저장소에 해당 값을 저장 하는 일반 속성입니다 (예:).

 연결 된 종속성 속성은 개체와 해당 컨테이너 (예: `Button` 컨테이너에 있는 개체의 위치) 간의 관계를 설명 하는 "속성"을 나타내는 정적 Get 및 Set 메서드로 모델링 된 종속성 속성의 일종입니다. `Panel`

 스타일 지정, 트리거, 데이터 바인딩, 애니메이션, 동적 리소스 및 상속과 같은 WPF 기능을 지 원하는 속성이 필요한 경우 종속성 속성을 제공 ✔️ 합니다.

## <a name="dependency-property-design"></a>종속성 속성 디자인

 <xref:System.Windows.DependencyObject>종속성 속성을 구현할 때 또는 해당 하위 형식 중 하나에서 상속 ✔️ 합니다. 형식은 속성 저장소의 매우 효율적인 구현을 제공 하며 WPF 데이터 바인딩을 자동으로 지원 합니다.

 ✔️은 <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> 각 종속성 속성에 대해 인스턴스를 저장 하는 일반 CLR 속성 및 public static 읽기 전용 필드를 제공 합니다.

 ✔️는 인스턴스 메서드와를 호출 하 여 종속성 속성 <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> 을 구현 <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> 합니다.

 속성 이름에 "접미사로"를 사용 하 여 종속성 속성 정적 필드의 이름을 ✔️ 합니다.

 ❌ 코드에서 종속성 속성의 기본값을 명시적으로 설정 하지 마십시오. 대신 메타 데이터에 설정 합니다.

 속성 기본값을 명시적으로 설정 하는 경우 스타일 지정과 같은 일부 암시적인 방법으로 해당 속성을 설정 하지 못할 수 있습니다.

 ❌ 표준 코드 이외의 속성 접근자에 코드를 삽입 하 여 정적 필드에 액세스 하지 마십시오.

 스타일 지정은 정적 필드를 직접 사용 하기 때문에 스타일 지정과 같은 암시적 방법으로 속성을 설정한 경우에는 해당 코드가 실행 되지 않습니다.

 ❌ 보안 데이터를 저장 하는 데 종속성 속성을 사용 하지 마세요. 비공개 종속성 속성은 공개적으로 액세스할 수 있습니다.

## <a name="attached-dependency-property-design"></a>연결 된 종속성 속성 디자인

 이전 섹션에서 설명 하는 종속성 속성은 선언 형식의 기본 속성을 나타냅니다. 예를 들어 `Text` 속성은를 선언 하는의 속성입니다 `TextButton` . 특별 한 종류의 종속성 속성은 연결 된 종속성 속성입니다.

 연결 된 속성의 전형적인 예는 <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> 속성입니다. 속성은 단추의 (그리드) 열 위치를 나타내지만 단추가 표에 포함 되어 있는 경우에만 적합 하며,이는 그리드에 의해 단추에 "연결" 됩니다.

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

 연결 된 속성의 정의는 접근자가 정적 Get 및 Set 메서드로 표시 되는 경우를 제외 하 고는 일반 종속성 속성의 정의와 거의 비슷합니다.

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

 속성은 종종 유효성 검사 라는 기능을 구현 합니다. 유효성 검사 논리는 속성의 값을 변경 하려고 할 때 실행 됩니다.

 아쉽게도 종속성 속성 접근자는 임의의 유효성 검사 코드를 포함할 수 없습니다. 대신 속성 등록 중에 종속성 속성 유효성 검사 논리를 지정 해야 합니다.

 ❌ 속성의 접근자에 종속성 속성 유효성 검사 논리를 넣지 마세요. 대신, 메서드에 유효성 검사 콜백을 전달 `DependencyProperty.Register` 합니다.

## <a name="dependency-property-change-notifications"></a>종속성 속성 변경 알림

 ❌ 종속성 속성 접근자에서 변경 알림 논리를 구현 하지 마십시오. 종속성 속성에는에 대 한 변경 알림 콜백을 제공 하 여 사용 해야 하는 기본 제공 변경 알림 기능이 있습니다 <xref:System.Windows.PropertyMetadata> .

## <a name="dependency-property-value-coercion"></a>종속성 속성 값 강제 변환

 속성 setter에 지정 된 값이 setter에 의해 수정 되 고 속성 저장소가 실제로 수정 될 때 속성 강제 변환이 수행 됩니다.

 ❌ 종속성 속성 접근자에서 강제 변환 논리를 구현 하지 마십시오.

 종속성 속성은 기본 제공 강제 변환 기능을 포함 하며,에 대 한 강제 변환 콜백을 제공 하 여 사용할 수 있습니다 `PropertyMetadata` .

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임 워크 디자인 지침](index.md)
- [일반적인 디자인 패턴](common-design-patterns.md)
