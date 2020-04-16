---
title: x:Members 지시문
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: c751a4f1cdea8dce7ef5165f5225ab3a825c7344
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432727"
---
# <a name="xmembers-directive"></a>x:Members 지시문
상위 요소의 x:Class에 적용되는 태그에 정의된 멤버 집합을 보유합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Class="className">
<x:Members>
  oneOrMoreMembers
</x:Members
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`className`|XAML 프로덕션에 대한 지원 클래스 또는 partial 클래스의 이름입니다. 설명 부분을 참조하세요.|
|`oneOrMoreMembers`|멤버 정의를 나타내는 하나 이상의 개체 요소입니다. 일반적으로 이러한 `x:Property` 요소는 개체 요소입니다. 설명 부분을 참조하세요.|

## <a name="remarks"></a>설명

.NET XAML 서비스 구현에서는 에 대한 `x:Members`백업 클래스 또는 기본 멤버 구현이 없습니다. `x:Members`은 모든 형식의 멤버로 존재할 수 있는 특수 XAML 멤버입니다. XAML 노드 스트림에서 `x:Members` XAML 언어 `Members`XAML 네임스페이스에서 .라는 멤버로 표시됩니다. 멤버에는 `Members` 읽기 전용 `Member` 개체 의 일반 목록이 포함되어 있습니다. 일반적인 태그에서 개별 멤버는 `x:Property` 속성 요소로 지정됩니다. `x:Property`는 형식의 속성에 대해 특별히 보다 정확한 `x:Member`형식이며 에 할당할 수 있습니다. 자세한 내용은 [x:Property 지시문을](xproperty-directive.md)참조하십시오.

태그로 멤버 정의를 지정하기 위한 수단으로서 `x:Members`의 실제 사용을 지원하려면 멤버가 수정할 수 있는 클래스와 연결되어야 합니다. 의도한 모델은 `x:Members`가 `x:Class`를 지정하는 형식의 멤버로 존재하는 것입니다. 그러나 형식 및 멤버를 연결하거나 동적 멤버 정의를 생성하기 위한 메커니즘은 .NET XAML 서비스 수준에서 지원되지 않습니다. 이 작업은 XAML의 멤버 정의를 지원하는 애플리케이션 모델이 있는 개별 프레임워크에서 수행해야 합니다. 일반적으로 해당 기능을 지원하려면 XAML을 태그로 컴파일하고 코드 숨김과 통합하거나 XAML 어셈블리에서만 생성하는 MSBUILD 빌드 작업이 필요합니다.

## <a name="xmembers-for-windows-workflow-foundation"></a>x:Windows 워크플로 파운데이션멤버

Windows 워크플로 `x:Members` 재단의 경우 코드 숨김이 있는 활동 디자이너에 대해 XAML 또는 XAML-정의된 동적 멤버로 구성된 사용자 지정 활동의 멤버가 포함됩니다. 또한 XAML 프로덕션의 루트 요소에 `x:Class`를 지정해야 합니다. 이는 .NET XAML 서비스 수준에서 요구되는 것은 아니지만 일반적으로 사용자 지정 활동 및 Windows 워크플로 파운데이션 XAML을 지원하는 MSBUILD 빌드 작업에 의해 XAML 프로덕션이 로드될 때 요구 사항이 됩니다. `x:Members``x:Class`을 선언하는 개체 요소의 태그에서 첫 번째 자식 요소여야 합니다.
