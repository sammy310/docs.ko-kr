---
title: XAML을 위한 컬렉션 및 컬렉션 형식
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 4123b64545f7c47a96c4cae496046a89b7e576b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494625"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML을 위한 컬렉션 및 컬렉션 형식

이 항목 컬렉션을 지원 하 고 컬렉션 항목 요소는 부모 개체 요소나 속성 요소 자식으로 인스턴스화하는 XAML 구문을 지원에 사용 되는 형식의 속성을 정의 하는 방법을 설명 합니다.

## <a name="xaml-collection-concepts"></a>XAML 컬렉션 개념

개념적으로 XAML 개체 요소 범위 내에서 자식 항목이 여러 개 있습니다 또는 컬렉션으로 XAML 속성 요소를 구현 해야 하는 XAML의 관계입니다. 해당 컬렉션은 해당 관계에서 부모에 해당 하는 XAML 형식의 특정 XAML 속성을 사용 하 여 연결 되어야 합니다. 속성은 XAML 프로세서가 태그 지원 컬렉션 속성의 새로 추가 된 항목에 각 항목에 할당할 예상 하기 때문에 컬렉션 이어야 합니다.

XAML 언어 수준에서 지 원하는 컬렉션의 정확한 요구는 완벽 하 게 정의 되지 않았습니다. 컬렉션 목록 또는 사전 (하지만 둘 다) 수 있는 개념은 XAML 언어 수준에서 정의 됩니다 있지만 백업 유형을 나타내는 두 목록 또는 사전 XAML 언어에서 정의 되지 않았습니다.

.NET Framework XAML 서비스에서 XAML에서 지 원하는 컬렉션 개념이 더 명확 하 게.NET Framework 지원 형식으로 정의 됩니다. 특히, 컬렉션에 대 한 XAML 지원은 여러.NET Framework의 개념 및 목록 및 일반적인.NET Framework 프로그래밍에서 사전에 사용 되는 Api에 기반 합니다.

1. <xref:System.Collections.IList> 인터페이스 목록 컬렉션을 나타냅니다.

2. <xref:System.Collections.IDictionary> 인터페이스 사전 컬렉션을 나타냅니다.

3. <xref:System.Array> 배열 및 배열 지원 나타냅니다 <xref:System.Collections.IList> 메서드.

각 컬렉션 개념에서 호출 하는.NET Framework XAML 서비스 XAML 프로세서에는 `Add` 메서드는 특정 인스턴스의 컬렉션 속성의 형식입니다. 또는 serialization 시나리오에서 XAML 프로세서는 목록, 사전 또는 "항목" 각 컬렉션의 특정 개념을 기준으로 배열에서 찾은 각 항목에 대 한 개별 XAML 형식 인스턴스를 생성 합니다. 이들은: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; 명시적 <xref:System.Array.System%23Collections%23IList%23Item%2A> 에 대 한 <xref:System.Array>합니다.

## <a name="generic-collections"></a>제네릭 컬렉션

제네릭 컬렉션을 프로그래밍 하는 일반.NET Framework에 유용할 수 있습니다 및 XAML 컬렉션 속성에도 사용할 수 있습니다. 그러나 제네릭 인터페이스 <xref:System.Collections.Generic.IList%601> 하 고 <xref:System.Collections.Generic.IDictionary%602> 제네릭이 아닌 동일.NET Framework XAML 서비스 XAML 프로세서에서 식별할 수 없는 <xref:System.Collections.IList> 또는 <xref:System.Collections.IDictionary>합니다. 클래스에서 파생 하는 제네릭 컬렉션 속성 형식에 대 한 권장 되는 방법은 인터페이스를 구현 하는 대신 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Collections.Generic.Dictionary%602>합니다. 이러한 클래스는 제네릭이 아닌 인터페이스를 구현 하 고 있으므로 기본 구현에서 XAML 컬렉션에 대 한 필요한 지원이 포함 합니다.

## <a name="read-only-collections-and-initialization-logic"></a>읽기 전용 컬렉션 및 초기화 논리

.NET Framework 프로그래밍에서는 일반적인 디자인 패턴을 읽기 전용 컬렉션으로 컬렉션의 값을 보유 하는 모든 속성을 확인 합니다. 이 패턴을 보다 효율적으로 제어 컬렉션에 어떤 일이 생기 컬렉션 속성을 소유 하는 인스턴스 허용... 특히 패턴 속성을 설정 하 여 전체 기존 컬렉션의 실수로 인 한 대체를 방지 합니다. 이 패턴에서는 호출자가 사용 하 여 컬렉션에 대 한 액세스 해야 대신 수와 같은 컬렉션 형식 및/또는 관련 컬렉션 인터페이스를 지 원하는 메서드 또는 속성을 호출 하 여 <xref:System.Collections.IList>입니다.

이 패턴을 사용 하 여 읽기 전용 컬렉션 속성을 노출 하는 클래스는 빈 컬렉션을 보유 하는 속성을 먼저 초기화 해야 하는 것을 의미 합니다. 일반적으로 초기화 하는 클래스에 대 한 구성 동작의 일부로 수행 됩니다. XAML에 대 한 유용할 것이 중요 이러한 논리 항상 기본 생성자에 의해 참조 되는 XAML에는 일반적으로 속성을 처리 하기 전에 기본 생성자를 호출 하기 때문에 (컬렉션 속성 또는 그렇지 않은 경우).

## <a name="xaml-type-system-support-and-collections"></a>XAML 형식 시스템 지원 및 컬렉션

XAML을 구문 분석 하 고 채우거 나 컬렉션 속성을 직렬화 하는 기본 메커니즘을 넘어 XAML 형식 시스템에서.NET Framework XAML 서비스 구현 될 때 XAML 컬렉션에 관련 된 몇 가지 디자인 기능을 포함 합니다.

1. <xref:System.Xaml.XamlType.IsCollection%2A> XAML 형식 XAML 컬렉션 지원을 제공 하는 형식에서 지원 되는 경우 true를 반환 합니다.

2. <xref:System.Xaml.XamlType.IsDictionary%2A> 및 <xref:System.Xaml.XamlType.IsArray%2A> XAML 형식을 지원 되는 컬렉션 모드를 식별할 수 있습니다. 사용자 지정 XAML에 대 한 프로세서는 XAML 및.NET Framework XAML 서비스를 기반으로 하는 형식 시스템 있지만 기존 기반 <xref:System.Xaml.XamlWriter> 구현에서는 컬렉션 모드는 파악 해야 할 수도 있습니다는 방법에 대 한 호출을 확인 하기 위해 컬렉션 처리 합니다.

3. 이전 속성 값을 각각에 잠재적으로 영향을 받지 재정의 <xref:System.Xaml.XamlType.LookupCollectionKind%2A> XAML 형식입니다.
