---
description: '자세한 정보: .NET Framework 4 및 4.5에 추가 된 CLR 호스팅 인터페이스'
title: .NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: e7c5dd042822be8653d9c068e85a751aed622f06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799917"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스

이 섹션에서는 관리 되지 않는 호스트가 .NET Framework 4, .NET Framework 4.5 이상 버전의 CLR (공용 언어 런타임)을 해당 응용 프로그램에 통합 하는 데 사용할 수 있는 인터페이스에 대해 설명 합니다. 이러한 인터페이스는 호스트에서 런타임을 구성 하 고 프로세스로 로드 하는 메서드를 제공 합니다.  
  
 .NET Framework 4부터 모든 호스팅 인터페이스에는 다음과 같은 특징이 있습니다.  
  
- 수명 관리 ( `AddRef` 및 `Release` ), 캡슐화 (암시적 컨텍스트) 및 COM을 사용 `QueryInterface` 합니다.  
  
- , 또는와 같은 COM 형식을 사용 하지 `BSTR` 않습니다 `SAFEARRAY` `VARIANT` .  
  
- [CoCreateInstance 함수](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)를 사용 하는 아파트 모델, 집계 또는 레지스트리 활성화는 없습니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [ICLRAppDomainResourceMonitor 인터페이스](iclrappdomainresourcemonitor-interface.md)  
 응용 프로그램 도메인의 메모리 및 CPU 사용량을 검사 하는 메서드를 제공 합니다.  
  
 [ICLRDomainManager 인터페이스](iclrdomainmanager-interface.md)  
 호스트에서 기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자를 지정 하 고 초기화 속성을 지정할 수 있도록 합니다.  
  
 [ICLRGCManager2 인터페이스](iclrgcmanager2-interface.md)  
 [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 제공 합니다 .이 메서드를 사용 하면 호스트에서 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 보다 큰 값으로 설정할 수 있습니다 `DWORD` .  
  
 [ICLRMetaHost 인터페이스](iclrmetahost-interface.md)  
 특정 버전의 CLR을 반환 하 고, 모든 설치 된 Clr을 나열 하 고, 모든 in-process 런타임을 나열 하 고, 활성화 인터페이스를 반환 하 고, 어셈블리를 컴파일하는 데 사용 되는 CLR 버전을 검색 하는 메서드를 제공 합니다.  
  
 [ICLRMetaHostPolicy 인터페이스](iclrmetahostpolicy-interface.md)  
 정책 기준, 관리 되는 어셈블리, 버전 및 구성 파일을 기반으로 CLR 인터페이스를 제공 하는 [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) 메서드를 제공 합니다.  
  
 [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)  
 버전, 디렉터리 및 로드 상태를 포함 하 여 특정 런타임에 대 한 정보를 반환 하는 메서드를 제공 합니다.  
  
 [ICLRStrongName 인터페이스](iclrstrongname-interface.md)  
 강력한 이름을 사용 하 여 어셈블리에 서명 하는 데 사용할 기본 전역 정적 함수를 제공 합니다. 모든 [ICLRStrongName](iclrstrongname-interface.md) 메서드는 표준 COM hresult를 반환 합니다.  
  
 [ICLRStrongName2 인터페이스](iclrstrongname2-interface.md)  
 에서는 sha-1 512 384 256 (Secure Hash algorithm)의 SHA-2 그룹을 사용 하 여 강력한 이름을 만들 수 있는 기능을 제공 합니다.  
  
 [ICLRTask2 인터페이스](iclrtask2-interface.md)  
 는 [ICLRTask 인터페이스](iclrtask-interface.md)의 모든 기능을 제공 합니다. 또한는 현재 스레드에서 스레드 중단이 지연 될 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="related-sections"></a>관련 섹션  

 [사용되지 않는 CLR 호스팅 인터페이스 및 Coclass](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 .NET Framework 버전 1.0 및 1.1과 함께 제공 되는 호스팅 인터페이스에 대해 설명 합니다.  
  
 [CLR 호스팅 인터페이스](clr-hosting-interfaces.md)  
 .NET Framework 버전 2.0, 3.0 및 3.5와 함께 제공 되는 호스팅 인터페이스에 대해 설명 합니다.  
  
 [호스팅](index.md)  
 .NET Framework에서 호스팅을 도입 합니다.
