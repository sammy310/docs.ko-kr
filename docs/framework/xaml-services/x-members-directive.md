---
title: x:Members 지시문
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: d23e6b459af932e0a6f69309f26a1cce70a9d256
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938894"
---
# <a name="xmembers-directive"></a>x:Members 지시문
부모 요소의 x: 클래스에 적용 되는 태그에 정의 된 멤버 집합을 보유 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
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
|`oneOrMoreMembers`|멤버 정의 나타내는 하나 이상의 개체 요소입니다. 이들은 일반적으로 `x:Property` 개체 요소입니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 .NET Framework XAML 서비스 구현에서 지원 클래스 또는 없을 대 한 기본 멤버 구현을 `x:Members`합니다. `x:Members` 모든 형식에 구성원으로 존재할 수 있는 특별 한 XAML 멤버 임 XAML 노드 스트림에서 `x:Members` 라는 멤버로 표시 됩니다 `Members`, XAML 언어 XAML 네임 스페이스에서입니다. 멤버 `Members` 목록이 읽기 전용 제네릭 `Member` 개체입니다. 일반적인 태그의 개별 구성원으로 지정 됩니다 `x:Property` 속성 요소입니다. `x:Property` 특히 형식의 속성에 대 한 보다 정확한 형식이 며 할당할 `x:Member`합니다. 자세한 내용은 [X:property 지시문](x-property-directive.md)합니다.  
  
 태그로 멤버 정의를 지정하기 위한 수단으로서 `x:Members`의 실제 사용을 지원하려면 멤버가 수정할 수 있는 클래스와 연결되어야 합니다. 의도한 모델은 `x:Members`가 `x:Class`를 지정하는 형식의 멤버로 존재하는 것입니다. 그러나 형식 및 멤버를 연결하거나 동적 멤버 정의를 생성하기 위한 메커니즘은 .NET Framework XAML 서비스 수준에서 지원되지 않습니다. 이 작업은 XAML의 멤버 정의를 지원하는 애플리케이션 모델이 있는 개별 프레임워크에서 수행해야 합니다. 일반적으로 해당 기능을 지원하려면 XAML을 태그로 컴파일하고 코드 숨김과 통합하거나 XAML 어셈블리에서만 생성하는 MSBUILD 빌드 작업이 필요합니다.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>Windows Workflow Foundation에 대 한 x: 멤버  
 Windows Workflow Foundation에 대 한 `x:Members` XAML, 또는 XAML에서 완전히 구성 된 사용자 지정 활동의 멤버를 포함 – 코드 숨김을 사용 하 여 activity designer에 대 한 동적 멤버를 정의 합니다. 또한 XAML 프로덕션의 루트 요소에 `x:Class`를 지정해야 합니다. 이는 .NET Framework XAML 서비스 수준에서의 요구 사항은 아니지만 사용자 지정 활동과 Windows Workflow Foundation XAML을 일반적으로 지원하는 MSBUILD 빌드 작업에 의해 XAML 프로덕션이 로드될 때 요구 사항이 됩니다. `x:Members` 선언 하는 개체 요소 태그에서 첫 번째 자식 요소 여야 합니다 `x:Class`합니다.
