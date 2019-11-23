---
title: 프로파일링 환경 설정
ms.date: 03/30/2017
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
ms.openlocfilehash: 86720cb1739e3f193cd1d5081577d69bca1cf0f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427056"
---
# <a name="setting-up-a-profiling-environment"></a>프로파일링 환경 설정
> [!NOTE]
> There have been substantial changes to profiling in the .NET Framework 4.  
  
 관리되는 프로세스(애플리케이션 또는 서비스)가 시작되면 CLR(공용 언어 런타임)을 로드합니다. CLR이 초기화되면 다음 두 가지 환경 변수를 평가하여 프로세스를 프로파일러에 연결해야 할지를 결정합니다.  
  
- COR_ENABLE_PROFILING: 이 환경 변수가 있고 1로 설정될 경우에만 CLR이 프로파일러에 연결됩니다.  
  
- COR_PROFILER: COR_ENABLE_PROFILING 확인에 통과하면 이전에 레지스트리에 저장되었어야 하는 이 CLSID 또는 ProgID를 포함하는 프로파일러에 CLR이 연결됩니다. COR_PROFILER 환경 변수는 다음 두 가지 예제와 같이 문자열로 정의됩니다.  
  
    ```cpp  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 CLR 애플리케이션을 프로파일링하려면 애플리케이션을 실행하기 전에 COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정해야 합니다. 또한 프로파일러 DLL이 등록되었는지 확인해야 합니다.  
  
> [!NOTE]
> Starting with the .NET Framework 4, profilers do not have to be registered.  
  
> [!NOTE]
> To use .NET Framework versions 2.0, 3.0, and 3.5 profilers in the .NET Framework 4 and later versions, you must set the COMPLUS_ProfAPI_ProfilerCompatibilitySetting environment variable.  
  
## <a name="environment-variable-scope"></a>환경 변수 범위  
 COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정하는 방법에 따라 영향을 미치는 범위가 결정됩니다. 다음 방법의 하나로 이들 변수를 설정할 수 있습니다.  
  
- If you set the variables in an [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) call, they will apply only to the application that you are running at the time. 변수는 환경을 상속하는 해당 애플리케이션에 의해 시작된 기타 애플리케이션에도 적용됩니다.  
  
- 명령 프롬프트 창에서 변수를 설정하면 해당 창에서 시작된 모든 애플리케이션에 변수가 적용됩니다.  
  
- 사용자 수준에서 변수를 설정하는 경우 파일 탐색기로 시작하는 모든 애플리케이션에 해당 변수가 적용됩니다. 변수를 설정하고 나서 연 명령 프롬프트 창에는 이 환경 설정이 포함되고 해당 창에서 시작하는 모든 애플리케이션도 포함됩니다. To set environment variables at the user level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, and add the variables to the **User variables** list.  
  
- 컴퓨터 수준에서 변수를 설정하는 경우 해당 컴퓨터에서 시작되는 모든 애플리케이션에 해당 변수가 적용됩니다. 해당 컴퓨터에서 연 명령 프롬프트 창에는 이 환경 설정이 포함되고 해당 창에서 시작하는 모든 애플리케이션도 포함됩니다. 즉, 해당 컴퓨터의 모든 관리되는 프로세스가 프로파일러를 사용하여 시작됩니다. To set environment variables at the computer level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, add the variables to the **System variables** list, and then restart your computer. 다시 시작하고 나면 변수를 시스템 수준에서 사용할 수 있습니다.  
  
 Windows 서비스를 프로파일링할 경우 환경 변수를 설정하고 프로파일러 DLL을 등록하고 나서 컴퓨터를 다시 시작해야 합니다. For more information about these considerations, see the section [Profiling a Windows Service](#windows_service).  
  
## <a name="additional-considerations"></a>추가 고려 사항  
  
- The profiler class implements the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces. .NET Framework 버전 2.0에서 프로파일러는 `ICorProfilerCallback2`를 구현해야 합니다. 구현하지 않으면 `ICorProfilerCallback2`가 로드되지 않습니다.  
  
- 특정 환경에서 한 번에 한 프로파일러에서만 프로세스를 프로파일링할 수 있습니다. 두 가지 프로파일러를 서로 다른 환경에서 등록할 수 있지만 각 프로파일러는 개별 프로세스를 프로파일링해야 합니다. 프로파일러는 프로파일링되고 있는 프로세스와 같은 주소 공간으로 매핑되는 in-process COM 서버 DLL로 구현되어야 합니다. 이는 프로파일러가 in-process로 실행됨을 의미합니다. .NET Framework는 다른 형식의 COM 서버를 지원하지 않습니다. 예를 들어 프로파일러가 원격 컴퓨터에서 애플리케이션을 모니터링하려고 하면 프로파일러가 각 컴퓨터에서 수집기 에이전트를 구현해야 합니다. 이들 에이전트를 결과를 일괄 처리하고 중앙 데이터 수집 컴퓨터에 전달합니다.  
  
- 프로파일러는 in-process로 인스턴스화되는 COM 개체이므로 각 프로파일링된 애플리케이션에는 자체 프로파일러 복사본이 있습니다. 따라서 단일 프로파일러 인스턴스는 여러 애플리케이션에서 데이터를 처리할 필요가 없습니다. 그러나 다른 프로파일링된 애플리케이션에서 로그 파일을 덮어쓰지 않도록 방지하려면 프로파일러의 로깅 코드에 논리를 추가해야 합니다.  
  
## <a name="initializing-the-profiler"></a>프로파일러 초기화  
 두 가지 환경 변수 확인을 모두 통과하면 CLR에서는 COM `CoCreateInstance` 함수와 비슷한 방식으로 프로파일러의 인스턴스를 만듭니다. 프로파일러는 직접 호출을 통해 `CoCreateInstance`에 로드되지 않습니다. 따라서 스레딩 모델을 설정해야 하는 `CoInitialize`가 호출되지 않습니다. The CLR then calls the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method in the profiler. 이 메서드의 서명은 다음과 같습니다.  
  
```cpp  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 The profiler must query `pICorProfilerInfoUnk` for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interface pointer and save it so that it can request more information later during profiling.  
  
## <a name="setting-event-notifications"></a>이벤트 알림 설정  
 The profiler then calls the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to specify which categories of notifications it is interested in. 예를 들어 프로파일러가 함수 시작 및 종료 알림과 가비지 수집 알림에만 관심이 있으면 다음을 지정합니다.  
  
```cpp  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 이 방식으로 알림 마스크를 설정하면 프로파일러는 수신하는 알림을 제한할 수 있습니다. 이 접근 방식을 통해 사용자가 단순 또는 특수 목적용 프로파일러를 빌드할 수 있습니다. 이를 통해 프로파일러가 무시하는 알림을 보내는 데 사용되는 CPU 시간이 감소합니다.  
  
 특정 프로파일러 이벤트는 변경할 수 없습니다. 즉, 이들 이벤트는 `ICorProfilerCallback::Initialize` 콜백에서 설정되고 난 직후에 해제할 수 없고 새 이벤트를 설정할 수 없습니다. 변경할 수 없는 이벤트를 변경하려고 하면 `ICorProfilerInfo::SetEventMask`에서 실패한 HRESULT가 반환됩니다.  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a>Windows 서비스 프로파일링  
 Windows 서비스 프로파일링은 공용 언어 런타임 애플리케이션 프로파일링과 비슷합니다. 두 가지 프로파일링 작업은 모두 환경 변수를 통해 사용하도록 설정됩니다. 운영 체제가 시작될 때 Windows 서비스가 시작되므로 이 항목의 앞에서 설명한 환경 변수가 이미 있고 시스템이 시작되기 전에 필요한 값으로 설정되어야 합니다. 또한 프로파일링 DLL이 시스템에 등록되어 있어야 합니다.  
  
 the COR_ENABLE_PROFILING 및 COR_PROFILER 환경 변수를 설정하고 프로파일러 DLL을 등록하고 나서 Windows 서비스가 해당 변경 내용을 감지할 수 있도록 대상 컴퓨터를 다시 시작해야 합니다.  
  
 이 변경을 통해 프로파일링이 시스템 전반에서 사용됩니다. 나중에 실행되는 모든 관리되는 애플리케이션이 프로파일링되지 않게 하려면 대상 컴퓨터를 다시 사직하고 나서 시스템 환경 변수를 삭제해야 합니다.  
  
 이 방법을 사용하면 모든 CLR 프로세스도 프로파일링됩니다. The profiler should add logic to its [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback to detect whether the current process is of interest. 관심이 없으면 프로파일러는 초기화를 수행하지 않고 콜백을 오류로 처리할 수 있습니다.  
  
## <a name="see-also"></a>참조

- [프로파일링 개요](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)
