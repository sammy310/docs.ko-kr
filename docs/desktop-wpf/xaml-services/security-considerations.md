---
title: XAML 보안 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432919"
---
# <a name="xaml-security-considerations"></a>XAML 보안 고려 사항

이 문서에서는 XAML 및 .NET XAML 서비스 API를 사용할 때 응용 프로그램의 보안에 대한 모범 사례를 설명합니다.

## <a name="untrusted-xaml-in-applications"></a>응용 프로그램에서 신뢰할 수 없는 XAML

가장 일반적인 의미에서 신뢰할 수 없는 XAML은 응용 프로그램에 특별히 포함하거나 내포함하지 않은 모든 XAML 소스입니다.

XAML은 신뢰할 수 있고 서명된 어셈블리 내에서 `resx`-형식 리소스로 컴파일또는 저장되는 것은 본질적으로 신뢰할 수 없습니다. 어셈블리 전체를 신뢰하는 만큼 XAML을 신뢰할 수 있습니다. 대부분의 경우 스트림 또는 기타 I/O에서 로드하는 XAML 소스인 느슨한 XAML의 트러스트 측면만 염려합니다. 느슨한 XAML은 배포 및 패키징 인프라가 있는 응용 프로그램 모델의 특정 구성 요소 또는 기능이 아닙니다. 그러나 어셈블리는 느슨한 XAML로드와 관련된 동작을 구현할 수 있습니다.

신뢰할 수 없는 XAML의 경우 일반적으로 신뢰할 수 없는 코드인 것처럼 처리해야 합니다. 샌드박싱 또는 기타 은유를 사용하여 신뢰할 수 없는 XAML이 신뢰할 수 있는 코드에 액세스하지 못하도록 합니다.

XAML 기능의 특성으로 인해 XAML은 개체를 생성하고 해당 속성을 설정할 수 있습니다. 이러한 기능에는 형식 변환기 액세스, 응용 프로그램 도메인의 어셈블리 매핑 및 `x:Code` 액세스, 태그 확장, 블록 등을 사용하는 것도 포함됩니다.

XAML은 언어 수준 기능 외에도 많은 기술에서 UI 정의에 사용됩니다. 신뢰할 수 없는 XAML을 로드하면 악의적인 스푸핑 UI가 로드될 수 있습니다.

## <a name="sharing-context-between-readers-and-writers"></a>독자와 기록기 간의 컨텍스트 공유

XAML 판독기 및 XAML 작성기를 위한 .NET XAML 서비스 아키텍처는 XAML 판독기를 XAML 기록기 또는 공유 XAML 스키마 컨텍스트에 공유해야 하는 경우가 많습니다. XAML 노드 루프 논리를 작성하거나 사용자 지정 저장 경로를 제공하는 경우 개체 또는 컨텍스트를 공유해야 할 수 있습니다. XAML 판독기 인스턴스, 기본이 아닌 XAML 스키마 컨텍스트 또는 XAML 판독기/작성기 클래스에 대한 설정을 신뢰할 수 있는 코드와 신뢰할 수 없는 코드 간에 공유하지 마십시오.

CLR 기반 형식 백업에 대한 XAML 개체 작성과 관련된 대부분의 시나리오 및 작업은 기본 XAML 스키마 컨텍스트만 사용할 수 있습니다. 기본 XAML 스키마 컨텍스트에는 완전 신뢰를 손상시킬 수 있는 설정이 명시적으로 포함되지 않습니다. 따라서 신뢰할 수 있는 XAML 판독기/작성기 구성 요소 간에 컨텍스트를 공유 해도 안전 합니다. 그러나 이렇게 하면 해당 판독기와 작성기를 별도의 <xref:System.AppDomain> 범위에 두는 것이 가장 좋은 방법입니다.

## <a name="xaml-namespaces-and-assembly-trust"></a>XAML 네임스페이스 및 어셈블리 트러스트

XAML이 사용자 지정 XAML 네임스페이스 매핑을 어셈블리로 해석하는 방법에 대한 기본 비정규구 및 정의는 응용 프로그램 도메인에 로드될 때 신뢰할 수 있는 어셈블리와 신뢰할 수 없는 어셈블리를 구분하지 않습니다. 따라서 신뢰할 수 없는 어셈블리가 신뢰할 수 있는 어셈블리의 의도된 XAML 네임스페이스 매핑을 스푸핑하고 XAML 원본의 선언된 개체 및 속성 정보를 캡처하는 것이 기술적으로 가능합니다. 이러한 상황을 피하기 위한 보안 요구 사항이 있는 경우 다음 기술 중 하나를 사용하여 의도한 XAML 네임스페이스 매핑을 수행해야 합니다.

- 응용 프로그램의 XAML에서 만든 모든 XAML 네임스페이스 매핑에 강력한 이름을 가진 정규화된 어셈블리 이름을 사용합니다.

- XAML 판독기 및 XAML 개체 작성기에 <xref:System.Xaml.XamlSchemaContext> 대한 특정 을 생성하여 어셈블리 매핑을 고정 참조 어셈블리 집합으로 제한합니다. <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>을 참조하세요.

## <a name="xaml-type-mapping-and-type-system-access"></a>XAML 유형 매핑 및 유형 시스템 액세스

XAML은 CLR이 기본 CLR 형식 시스템을 구현하는 방법에 대한 여러 가지 면에서 피어인 자체 형식 시스템을 지원합니다. 그러나 형식 정보를 기반으로 형식에 대한 트러스트 결정을 내리는 형식 인식의 특정 측면에 대해서는 CLR 백업 형식의 형식 정보를 연기해야 합니다. 이는 XAML 형식 시스템의 일부 특정 보고 기능이 가상 메서드로 열려 있으므로 원래 .NET XAML 서비스 구현을 완전히 제어할 수 없기 때문입니다. 이러한 확장성 점은 XAML 형식 시스템이 확장가능하기 때문에 XAML 자체의 확장성 및 가능한 대체 형식 매핑 전략과 기본 CLR 지원 구현 및 기본 XAML 스키마 컨텍스트와 일치하기 때문에 존재합니다. 자세한 내용은 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>의 여러 속성에 대한 특정 메모를 참조하십시오.

## <a name="see-also"></a>참조

- <xref:System.Xaml.Permissions.XamlAccessLevel>
