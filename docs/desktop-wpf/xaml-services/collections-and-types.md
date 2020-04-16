---
title: XAML을 위한 컬렉션 및 컬렉션 형식
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "81432583"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML에 대한 컬렉션 및 컬렉션 유형

이 문서에서는 컬렉션을 지원하기 위한 형식의 속성을 정의하고 컬렉션 항목을 상위 개체 요소 또는 속성 요소의 요소 자식으로 인스턴스화하기 위한 XAML 구문을 지원하는 방법을 설명합니다.

## <a name="xaml-collection-concepts"></a>XAML 컬렉션 컨셉

개념적으로 XAML 개체 요소 또는 XAML 속성 요소의 범위 내에 여러 자식 항목이 있는 XAML의 모든 관계는 컬렉션으로 구현되어야 합니다. 해당 컬렉션은 해당 관계의 부모인 XAML 형식의 특정 XAML 속성과 연결되어야 합니다. XAML 프로세서가 태그의 각 항목을 백업 컬렉션 속성의 새로 추가된 항목으로 할당할 것으로 예상되므로 속성은 컬렉션이어야 합니다.

XAML 언어 수준에서 컬렉션 지원의 정확한 요구 사항은 완전히 정의되지 않습니다. 컬렉션이 목록 또는 사전일 수 있다는 개념은 XAML 언어 수준에서 정의되지만 목록 또는 사전을 나타내는 백업 형식은 XAML 언어로 정의되지 않습니다.

.NET XAML 서비스에서 XAML 컬렉션 지원의 개념은 .NET 백업 형식측면에서 보다 명확하게 정의됩니다. 특히 컬렉션에 대한 XAML 지원은 일반 .NET 프로그래밍의 목록 및 사전에 사용되는 여러 .NET 개념 및 API를 기반으로 합니다.

1. 인터페이스는 <xref:System.Collections.IList> 목록 컬렉션을 나타냅니다.

2. 인터페이스는 <xref:System.Collections.IDictionary> 사전 컬렉션을 나타냅니다.

3. <xref:System.Array>는 배열을 나타내며 <xref:System.Collections.IList> 배열은 메서드를 지원합니다.

이러한 각 컬렉션 개념에서 .NET XAML 서비스 XAML 프로세서는 `Add` 컬렉션 속성 의 형식의 특정 인스턴스에서 메서드를 호출할 것으로 예상합니다. 또는 직렬화 시나리오에서 XAML 프로세서는 각 컬렉션의 특정 개념인 "Items"를 기반으로 목록, 사전 또는 배열에 있는 각 항목에 대해 개별 XAML 형식 인스턴스를 생성합니다. 이러한 항목은 <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType>다음과 같습니다. <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType>; 에 <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> 대한 <xref:System.Array>명시적 입니다.

## <a name="generic-collections"></a>제네릭 컬렉션

일반 컬렉션은 일반 .NET 프로그래밍에 유용할 수 있으며 XAML 컬렉션 속성에도 사용할 수 있습니다. 그러나 일반 <xref:System.Collections.Generic.IList%601> 인터페이스및 <xref:System.Collections.Generic.IDictionary%602> .NET XAML 서비스 XAML 프로세서에 의해 비제네릭 <xref:System.Collections.IList> 또는 <xref:System.Collections.IDictionary>에 해당되는 것으로 식별되지 않습니다. 인터페이스를 구현하는 대신 제네릭 컬렉션 속성 형식에 대한 권장 <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.Dictionary%602>방법은 클래스 또는 에서 파생하는 것입니다. 이러한 클래스는 비일반 인터페이스를 구현하므로 기본 구현에서 XAML 컬렉션에 대한 예상 지원이 포함됩니다.

## <a name="read-only-collections-and-initialization-logic"></a>읽기 전용 컬렉션 및 초기화 논리

.NET 프로그래밍에서는 컬렉션값을 포함하는 속성을 읽기 전용 컬렉션으로 만드는 일반적인 디자인 패턴입니다. 이 패턴을 사용하면 컬렉션 속성을 소유하는 인스턴스가 컬렉션에 발생하는 작업을 더 잘 제어할 수 있습니다. 특히 이 패턴은 속성을 설정하여 기존 컬렉션 전체를 실수로 교체하는 것을 방지합니다. 이 패턴에서는 호출자가 컬렉션에 대한 모든 액세스 권한을 호출하는 대신 컬렉션 형식 및/또는 와 같은 <xref:System.Collections.IList>관련 컬렉션 인터페이스에서 지원하는 메서드 또는 속성을 호출하여 수행해야 합니다.

이 패턴을 사용 하 여 읽기 전용 컬렉션 속성을 노출 하는 모든 클래스 먼저 빈 컬렉션을 보유 하는 해당 속성을 초기화 해야 합니다. 일반적으로 초기화는 클래스에 대한 구성 동작의 일부로 수행됩니다. XAML에 유용하려면 XAML이 일반적으로 속성(컬렉션 속성 또는 기타)을 처리하기 전에 매개 변수 없는 생성자를 호출하기 때문에 이러한 논리를 항상 매개 변수 없는 생성자에서 참조하는 것이 중요합니다.

## <a name="xaml-type-system-support-and-collections"></a>XAML 유형 시스템 지원 및 컬렉션

.NET XAML 서비스에서 구현된 XAML 형식 시스템에는 XAML 을 구문 분석하고 컬렉션 속성을 채우거나 직렬화하는 기본 메커니즘 외에도 XAML의 컬렉션과 관련된 몇 가지 디자인 기능이 포함되어 있습니다.

1. <xref:System.Xaml.XamlType.IsCollection%2A>XAML 형식이 XAML 컬렉션 지원을 제공하는 형식에 의해 백업되는 경우 true를 반환합니다.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>또한 <xref:System.Xaml.XamlType.IsArray%2A> XAML 유형이 지원하는 컬렉션 모드를 식별할 수 있습니다. .NET XAML 서비스 및 XAML 형식 시스템을 기반으로 하지만 기존 <xref:System.Xaml.XamlWriter> 구현을 기반으로 하지 않는 사용자 지정 XAML 프로세서의 경우 컬렉션 처리를 위해 호출할 메서드를 알기 위해 사용되는 컬렉션 모드를 아는 것이 필요할 수 있습니다.

3. 각 이전 속성 값은 XAML 형식의 <xref:System.Xaml.XamlType.LookupCollectionKind%2A> 재정의에 의해 영향을 받습니다.
