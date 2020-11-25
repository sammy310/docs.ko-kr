---
title: CLR 호스팅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: 77f2ba64d9bdbe9793d56e88dae46fd506119ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719049"
---
# <a name="clr-hosting-interfaces"></a>CLR 호스팅 인터페이스

이 섹션에서는 관리 되지 않는 호스트가 CLR (공용 언어 런타임)을 응용 프로그램에 통합 하는 데 사용할 수 있는 인터페이스에 대해 설명 합니다. 이 정보는 .NET Framework 버전 2.0 이상 버전과 관련이 있습니다. 이러한 인터페이스를 통해 호스트는 버전 1.0 및 1.1에서 제공 되는 것 보다 많은 버전의 런타임을 제어할 수 있으며 CLR과 호스트의 실행 모델 간에 훨씬 긴밀 한 통합을 제공 합니다.  
  
 .NET Framework 버전 1.0 및 1.1에서 호스팅 모델은 관리 되지 않는 호스트에서 CLR을 프로세스로 로드 하 여 특정 설정을 구성 하 고 이벤트 알림을 수신 하도록 설정 했습니다. 그러나 일반적으로 호스트와 CLR은 해당 프로세스에서 독립적으로 실행 됩니다. .NET Framework 버전 2.0 이상 버전에서는 새 추상화 계층이 호스트에서 Win32 어셈블리의 형식으로 현재 제공 된 많은 리소스를 제공 하 고 호스트가 구성할 수 있는 기능 집합을 확장할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [IActionOnCLREvent 인터페이스](iactiononclrevent-interface.md)  
 등록 된 이벤트에 대해 콜백을 수행 하는 메서드를 제공 합니다.  
  
 [IApartmentCallback 인터페이스](iapartmentcallback-interface.md)  
 아파트 내에서 콜백을 만드는 메서드를 제공 합니다.  
  
 [IAppDomainBinding 인터페이스](iappdomainbinding-interface.md)  
 런타임 구성을 설정 하기 위한 메서드를 제공 합니다.  
  
 [ICatalogServices 인터페이스](icatalogservices-interface.md)  
 카탈로그 서비스에 대 한 메서드를 제공 합니다. 이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)  
  
 [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)  
 어셈블리에 대 한 호스트와 CLR 간의 통신을 지 원하는 메서드를 제공 합니다.  
  
 [ICLRAssemblyReferenceList 인터페이스](iclrassemblyreferencelist-interface.md)  
 호스트가 아닌 CLR에서 로드 하는 어셈블리 목록을 관리 합니다.  
  
 [ICLRControl 인터페이스](iclrcontrol-interface.md)  
 호스트에서 CLR의 다양 한 측면에 대 한 액세스를 얻고 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRDebugManager 인터페이스](iclrdebugmanager-interface.md)  
 호스트에서 작업 집합을 식별자와 이름에 연결할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)  
 호스트에서 오류 보고를 위해 사용자 지정 힙 덤프를 구성할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRGCManager 인터페이스](iclrgcmanager-interface.md)  
 호스트가 CLR의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRHostBindingPolicyManager 인터페이스](iclrhostbindingpolicymanager-interface.md)  
 호스트에서 어셈블리의 정책 정보에 대 한 변경 내용을 평가 하 고 전달 하는 메서드를 제공 합니다.  
  
 [ICLRHostProtectionManager 인터페이스](iclrhostprotectionmanager-interface.md)  
 호스트에서 특정 관리 되는 클래스, 메서드, 속성 및 필드가 부분적으로 신뢰할 수 있는 코드에서 실행 되는 것을 차단할 수 있도록 합니다.  
  
 [ICLRIoCompletionManager 인터페이스](iclriocompletionmanager-interface.md)  
 호스트에서 지정 된 i/o 요청의 상태를 CLR에 알릴 수 있도록 하는 콜백 메서드를 구현 합니다.  
  
 [ICLRMemoryNotificationCallback 인터페이스](iclrmemorynotificationcallback-interface.md)  
 호스트에서 Win32 함수와 유사한 방법을 사용 하 여 메모리 압력 상태를 보고할 수 있도록 합니다 `CreateMemoryResourceNotification` .  
  
 [ICLROnEventManager 인터페이스](iclroneventmanager-interface.md)  
 호스트가 CLR 이벤트의 콜백을 등록 하 고 등록 취소할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)  
 호스트에서 오류 및 시간 제한이 발생 하는 경우 수행할 정책 작업을 지정할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRProbingAssemblyEnum 인터페이스](iclrprobingassemblyenum-interface.md)  
 호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR의 내부에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져올 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRReferenceAssemblyEnum 인터페이스](iclrreferenceassemblyenum-interface.md)  
 호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR 내부의 어셈블리 id 데이터를 사용 하 여 파일이 나 스트림이 참조 하는 어셈블리 집합을 조작할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRRuntimeHost 인터페이스](iclrruntimehost-interface.md)  
 호스트 컨트롤 인터페이스를 설정 하는 추가 메서드를 사용 하 여 [ICorRuntimeHost](icorruntimehost-interface.md)와 유사한 기능을 제공 합니다.  
  
 [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)  
 호스트에서 요청 된 작업에 대 한 정보를 가져오고 해당 동기화 구현에서 교착 상태를 검색 하는 메서드를 제공 합니다.  
  
 [ICLRTask 인터페이스](iclrtask-interface.md)  
 호스트가 CLR의 요청을 하거나 연결 된 작업에 대 한 알림을 CLR에 제공할 수 있도록 하는 메서드를 제공 합니다.  
  
 [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)  
 호스트가 새 작업을 만들고, 현재 실행 중인 작업을 가져오고, 작업의 지리적 언어와 문화권을 설정 하는 작업을 명시적으로 요청 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [ICLRValidator 인터페이스](iclrvalidator-interface.md)  
 PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.  
  
 [ICorConfiguration 인터페이스](icorconfiguration-interface.md)  
 CLR을 구성 하기 위한 메서드를 제공 합니다.  
  
 [ICorThreadpool 인터페이스](icorthreadpool-interface.md)  
 스레드 풀에 액세스 하기 위한 메서드를 제공 합니다.  
  
 [IDebuggerInfo 인터페이스](idebuggerinfo-interface.md)  
 디버깅 서비스의 상태에 대 한 정보를 가져오는 메서드를 제공 합니다.  
  
 [IDebuggerThreadControl 인터페이스](idebuggerthreadcontrol-interface.md)  
 디버깅 서비스에서 스레드의 차단 및 차단 해제에 대해 호스트에 알리는 메서드를 제공 합니다.  
  
 [IGCHost 인터페이스](igchost-interface.md)  
 가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.  
  
 [IGCHost2 인터페이스](igchost2-interface.md)  
 [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) 메서드를 제공 합니다 .이 메서드를 사용 하면 호스트에서 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 0 보다 큰 값으로 설정할 수 있습니다 `DWORD` .  
  
 [IGCHostControl 인터페이스](igchostcontrol-interface.md)  
 가비지 수집기에서 호스트에 가상 메모리의 제한을 변경 하도록 요청할 수 있는 메서드를 제공 합니다.  
  
 [IGCThreadControl 인터페이스](igcthreadcontrol-interface.md)  
 가비지 수집에 대해 차단 될 스레드 예약에 참여 하기 위한 메서드를 제공 합니다.  
  
 [IHostAssemblyManager 인터페이스](ihostassemblymanager-interface.md)  
 호스트가 CLR 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostAssemblyStore 인터페이스](ihostassemblystore-interface.md)  
 호스트가 CLR과는 독립적으로 어셈블리 및 모듈을 로드할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IHostAutoEvent 인터페이스](ihostautoevent-interface.md)  
 호스트에서 구현 하는 자동 다시 설정 이벤트의 표현을 제공 합니다.  
  
 [IHostControl 인터페이스](ihostcontrol-interface.md)  
 어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.  
  
 [IHostCrst 인터페이스](ihostcrst-interface.md)  
 스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.  
  
 [IHostGCManager 인터페이스](ihostgcmanager-interface.md)  
 CLR에서 구현 하는 가비지 수집 메커니즘에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.  
  
 [IHostIoCompletionManager 인터페이스](ihostiocompletionmanager-interface.md)  
 CLR이 호스트에서 제공 하는 i/o 완료 포트와 상호 작용할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IHostMalloc 인터페이스](ihostmalloc-interface.md)  
 호스트를 통해 힙에서 세분화 된 할당을 요청 하는 메서드를 제공 합니다.  
  
 [IHostManualEvent 인터페이스](ihostmanualevent-interface.md)  
 수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.  
  
 [IHostMemoryManager 인터페이스](ihostmemorymanager-interface.md)  
 표준 Win32 가상 메모리 함수를 사용 하는 대신 호스트를 통해 가상 메모리 요청을 만드는 CLR에 대 한 메서드를 제공 합니다.  
  
 [IHostPolicyManager 인터페이스](ihostpolicymanager-interface.md)  
 중단, 시간 초과 또는 오류가 발생 하는 경우 CLR에서 수행 하는 작업을 호스트에 알리는 메서드를 제공 합니다.  
  
 [IHostSecurityContext 인터페이스](ihostsecuritycontext-interface.md)  
 CLR에서 호스트에 의해 구현 된 보안 컨텍스트 정보를 유지 관리할 수 있도록 합니다.  
  
 [IHostSecurityManager 인터페이스](ihostsecuritymanager-interface.md)  
 현재 실행 중인 스레드의 보안 컨텍스트에 대 한 액세스 및 제어를 허용 하는 메서드를 제공 합니다.  
  
 [IHostSemaphore 인터페이스](ihostsemaphore-interface.md)  
 호스트에서 구현 하는 세마포 표현을 제공 합니다.  
  
 [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)  
 CLR에서 Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 동기화 기본 형식을 만드는 데 사용할 수 있는 메서드를 제공 합니다.  
  
 [IHostTask 인터페이스](ihosttask-interface.md)  
 CLR이 호스트와 통신 하 여 작업을 관리할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)  
 CLR이 표준 운영 체제 스레딩 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 수행할 수 있도록 하는 메서드를 제공 합니다.  
  
 [IHostThreadPoolManager 인터페이스](ihostthreadpoolmanager-interface.md)  
 CLR이 스레드 풀을 구성 하 고 작업 항목을 스레드 풀에 대기 시킬 수 있는 메서드를 제공 합니다.  
  
 [IManagedObject 인터페이스](imanagedobject-interface.md)  
 관리 되는 개체를 제어 하는 메서드를 제공 합니다.  
  
 IObjectHandle  
 간접 참조에서 값으로 마샬링하는 개체를 래핑 해제 하는 메서드를 제공 합니다.  
  
 [ITypeName 인터페이스](itypename-interface.md)  
 형식 이름 정보를 가져오는 메서드를 제공 합니다. 이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)  
  
 [ITypeNameBuilder 인터페이스](itypenamebuilder-interface.md)  
 형식 이름을 빌드하기 위한 메서드를 제공 합니다. 이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)  
  
 [ITypeNameFactory 인터페이스](itypenamefactory-interface.md)  
 형식 이름을 분해 하는 메서드를 제공 합니다. 이 인터페이스는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)  
  
 IValidator  
 PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  

 [사용되지 않는 CLR 호스팅 인터페이스 및 Coclass](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 .NET Framework 버전 1.0 및 1.1에 제공 된 호스팅 인터페이스를 설명 하는 항목을 포함 합니다.  
  
 [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 .NET Framework 4에서 제공 하는 호스팅 인터페이스를 설명 하는 항목을 포함 합니다.
