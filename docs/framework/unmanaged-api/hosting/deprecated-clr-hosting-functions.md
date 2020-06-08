---
title: 사용되지 않는 CLR 호스팅 함수
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504370"
---
# <a name="deprecated-clr-hosting-functions"></a>사용되지 않는 CLR 호스팅 함수
이 섹션에서는 이전 버전의 호스팅 API가 사용 하는 관리 되지 않는 전역 정적 함수에 대해 설명 합니다.  
  
 .NET Framework에만 사용 되는 인프라 함수 (함수)를 제외 하 고 `_Cor*` , 이러한 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="activation-functions"></a>활성화 함수  
 [ClrCreateManagedInstance 함수](clrcreatemanagedinstance-function.md)  
 사용되지 않습니다. 지정 된 관리 되는 형식의 인스턴스를 만듭니다.  
  
 [CoInitializeCor 함수](coinitializecor-function.md)  
 더 이상 사용되지 않습니다. CLR (공용 언어 런타임)을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.  
  
 [CoInitializeEE 함수](coinitializeee-function.md)  
 사용되지 않습니다. CLR 실행 엔진이 프로세스로 로드 되는지 확인 합니다. 대신 [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) 메서드를 사용 합니다.  
  
 [CorBindToCurrentRuntime 함수](corbindtocurrentruntime-function.md)  
 사용되지 않습니다. XML 파일에 저장 된 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.  
  
 [CorBindToRuntime 함수](corbindtoruntime-function.md)  
 사용되지 않습니다. 관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 합니다.  
  
 [CorBindToRuntimeByCfg 함수](corbindtoruntimebycfg-function.md)  
 사용되지 않습니다. XML 파일에서 읽은 버전 정보를 사용 하 여 CLR을 프로세스로 로드 합니다.  
  
 [CorBindToRuntimeEx 함수](corbindtoruntimeex-function.md)  
 사용되지 않습니다. 관리 되지 않는 호스트에서 CLR을 프로세스로 로드할 수 있도록 하 고, CLR의 동작을 지정 하는 플래그를 설정할 수 있도록 합니다.  
  
 [CorBindToRuntimeHost 함수](corbindtoruntimehost-function.md)  
 사용되지 않습니다. 호스트에서 지정 된 버전의 CLR을 프로세스로 로드할 수 있도록 합니다.  
  
 [GetCORRequiredVersion 함수](getcorrequiredversion-function.md)  
 사용되지 않습니다. 필요한 CLR 버전 번호를 가져옵니다.  
  
 [GetCORSystemDirectory 함수](getcorsystemdirectory-function.md)  
 사용되지 않습니다. 프로세스에 로드 된 CLR의 설치 디렉터리를 반환 합니다.  
  
 [GetRealProcAddress 함수](getrealprocaddress-function.md)  
 사용되지 않습니다. 최신 버전의 CLR에서 내보낸 지정 된 함수의 주소를 가져옵니다.  
  
 [GetRequestedRuntimeInfo 함수](getrequestedruntimeinfo-function.md)  
 사용되지 않습니다. 응용 프로그램에서 요청한 CLR에 대 한 버전 및 디렉터리 정보를 가져옵니다.  
  
## <a name="clr-version-functions"></a>CLR 버전 함수  
 이 단원의 함수는 CLR 버전을 반환 합니다. CLR을 활성화 하지 않습니다.  
  
 [GetCORVersion 함수](getcorversion-function.md)  
 사용되지 않습니다. 현재 프로세스에서 실행 중인 CLR의 버전 번호를 반환 합니다.  
  
 [GetFileVersion 함수](getfileversion-function.md)  
 사용되지 않습니다. 지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR 버전 정보를 가져옵니다.  
  
 [GetRequestedRuntimeVersion 함수](getrequestedruntimeversion-function.md)  
 사용되지 않습니다. 지정 된 응용 프로그램에서 요청한 CLR의 버전 번호를 가져옵니다. 해당 버전이 설치 되지 않은 경우는 요청 된 버전 보다 먼저 설치 된 최신 버전을 가져옵니다.  
  
 [GetRequestedRuntimeVersionForCLSID 함수](getrequestedruntimeversionforclsid-function.md)  
 사용되지 않습니다. 지정 된 CLSID를 사용 하 여 클래스에 대 한 적절 한 CLR 버전 정보를 가져옵니다.  
  
 [GetVersionFromProcess 함수](getversionfromprocess-function.md)  
 사용되지 않습니다. 지정 된 프로세스 핸들과 연결 된 CLR의 버전 번호를 가져옵니다.  
  
 [LockClrVersion 함수](lockclrversion-function.md)  
 사용되지 않습니다. 호스트에서 CLR을 명시적으로 초기화 하기 전에 프로세스 내에서 사용 되는 CLR 버전을 확인할 수 있습니다.  
  
## <a name="hosting-functions"></a>호스팅 함수  
 [CallFunctionShim 함수](callfunctionshim-function.md)  
 사용되지 않습니다. 지정 된 라이브러리에서 지정 된 이름 및 매개 변수를 가진 함수를 호출 합니다.  
  
 [CoEEShutDownCOM 함수](coeeshutdowncom-function.md)  
 사용되지 않습니다. 프로세스에서 COM 어셈블리를 언로드합니다.  
  
 [CorExitProcess 함수](corexitprocess-function.md)  
 사용되지 않습니다. 현재 관리 되지 않는 프로세스를 종료 합니다.  
  
 [CorLaunchApplication 함수](corlaunchapplication-function.md)  
 사용되지 않습니다. 지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.  
  
 [CorMarkThreadInThreadPool 함수](cormarkthreadinthreadpool-function.md)  
 사용되지 않습니다. 관리 코드 실행을 위해 현재 실행 중인 스레드 풀 스레드를 표시 합니다. .NET Framework 버전 2.0부터이 함수는 아무런 영향을 주지 않습니다. 필요 하지 않으며 코드에서 제거할 수 있습니다.  
  
 [CoUninitializeCor 함수](couninitializecor-function.md)  
 더 이상 사용되지 않습니다. CLR은 프로세스에서 언로드할 수 없습니다.  
  
 [CoUninitializeEE 함수](couninitializeee-function.md)  
 더 이상 사용되지 않습니다.  
  
 [CreateDebuggingInterfaceFromVersion 함수](createdebugginginterfacefromversion-function.md)  
 사용되지 않습니다. 지정 된 버전 정보를 기반으로 [ICorDebug](../debugging/icordebug-interface.md) 개체를 만듭니다.  
  
 [CreateICeeFileGen 함수](createiceefilegen-function.md)  
 사용되지 않습니다. [ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.  
  
 [DestroyICeeFileGen 함수](destroyiceefilegen-function.md)  
 사용되지 않습니다. [ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.  
  
 [FExecuteInAppDomainCallback 함수 포인터](fexecuteinappdomaincallback-function-pointer.md)  
 사용되지 않습니다. 관리 코드를 실행 하기 위해 CLR이 호출 하는 함수를 가리킵니다.  
  
 [FLockClrVersionCallback 함수 포인터](flockclrversioncallback-function-pointer.md)  
 사용되지 않습니다. 는 초기화가 시작 되거나 완료 되었음을 호스트에 알리기 위해 CLR에서 호출 하는 함수를 가리킵니다.  
  
 [GetCLRIdentityManager 함수](getclridentitymanager-function.md)  
 사용되지 않습니다. CLR에서 id를 관리할 수 있도록 하는 인터페이스에 대 한 포인터를 가져옵니다.  
  
 [LoadLibraryShim 함수](loadlibraryshim-function.md)  
 사용되지 않습니다. 지정 된 버전의 .NET Framework DLL을 로드 합니다.  
  
 [LoadStringRC 함수](loadstringrc-function.md)  
 사용되지 않습니다. 현재 스레드의 기본 문화권을 사용 하 여 HRESULT 값을 오류 메시지로 변환 합니다.  
  
 [LoadStringRCEx 함수](loadstringrcex-function.md)  
 사용되지 않습니다. HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.  
  
 [LPOVERLAPPED_COMPLETION_ROUTINE 함수 포인터](lpoverlapped-completion-routine-function-pointer.md)  
 사용되지 않습니다. 장치에 대해 겹치는 (즉, 비동기) i/o가 완료 되었을 때 호스트에 알리는 함수를 가리킵니다.  
  
 [LPTHREAD_START_ROUTINE 함수 포인터](lpthread-start-routine-function-pointer.md)  
 사용되지 않습니다. 스레드가 실행을 시작 했음을 호스트에 알리는 함수를 가리킵니다.  
  
 [RunDll32ShimW 함수](rundll32shimw-function.md)  
 사용되지 않습니다. 지정된 명령을 실행합니다.  
  
 [WAITORTIMERCALLBACK 함수 포인터](waitortimercallback-function-pointer.md)  
 사용되지 않습니다. 대기 핸들이 신호를 받았거나 시간이 초과 되었음을 호스트에 알리는 함수를 가리킵니다.  
  
## <a name="infrastructure-functions"></a>인프라 기능  
 이 섹션의 함수는 .NET Framework 에서만 사용할 수 있습니다.  
  
 [_CorDllMain 함수](cordllmain-function.md)  
 CLR을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.  
  
 [_CorExeMain 함수](corexemain-function.md)  
 CLR을 초기화 하 고, 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.  
  
 [_CorExeMain2 함수](corexemain2-function.md)  
 지정 된 메모리 매핑된 코드에서 진입점을 실행 합니다. 이 함수는 운영 체제 로더에 의해 호출 됩니다.  
  
 [_CorImageUnloading 함수](corimageunloading-function.md)  
 관리 되는 모듈 이미지가 언로드될 때 로더에 알립니다.  
  
 [_CorValidateImage 함수](corvalidateimage-function.md)  
 관리 되는 모듈 이미지의 유효성을 검사 하 고, 운영 체제 로더가 로드 된 후이를 알립니다.  
  
## <a name="see-also"></a>참고 항목

- [.NET Framework 4 호스팅 전역 정적 함수](net-framework-4-hosting-global-static-functions.md)
