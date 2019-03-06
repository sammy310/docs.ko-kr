---
title: CLR 프로파일러 및 Windows 스토어 앱
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93344e1c5aa62e86d29a0110a9d8cffc3cea66ff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358550"
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR 프로파일러 및 Windows 스토어 앱

이 항목에서는 쓰기 진단 도구 분석 하는 Windows 스토어 앱 내에서 실행 되는 코드를 관리 하는 경우에 대 한 고려해 야 하는 항목을 설명 합니다. 또한 Windows 스토어 앱에 대해 실행 하면 작업을 계속 하도록 기존 개발 도구를 수정 하기 위한 지침을 제공 합니다. 이 정보를 이해 하는 것이 좋습니다 올바르게에 대 한 Windows 데스크톱 응용 프로그램을 실행 하는 도구를 수정 하는 이제 관심이 있는 진단 도구에서이 API를 이미 사용 했습니다 공용 언어 런타임 프로 파일링 API에 익숙한 경우 Windows 스토어 앱에 대해 올바르게를 실행 합니다.

## <a name="introduction"></a>소개

소개 문단 지난 수행한 경우 다음 익숙한 CLR 프로 파일링 API. 관리 되는 데스크톱 응용 프로그램에 대해 작동 하는 진단 도구를 이미 작성 했습니다. 이제 궁금 하는 도구는 관리 되는 Windows 스토어 앱을 사용 하 여 작동 하도록 해야 할 일입니다. 아마도이 작업을 수행 하 여 간단한 작업 아닌지 검색 시도 이미 했습니다. 실제로 모든 도구 개발자가 명확 하지 않을 수 있는 고려 사항 많습니다. 예를 들어:

- Windows 스토어 앱 권한이 낮춰 진 심각 하 게 된 컨텍스트에서 실행 됩니다.

- Windows 메타 데이터 파일에는 기존의 관리 되는 모듈을 비교할 때 고유한 특징이 있습니다.

- Windows 스토어 앱에 대화형 작업을 중단 하는 경우에 자체 일시 중단 하는 습관이 있습니다.

- 프로세스 간 통신 메커니즘에는 다양 한 이유로 더 이상 작동할 수 없습니다.

이 항목에는 제대로 처리 하는 방법과 알아야 할 사항이 나와 있습니다.

CLR 프로 파일링 API를 처음 접하는 경우이 항목의 끝에 리소스를 더 잘 소개 정보를 찾을 수으로 건너뜁니다.

특정 Windows Api 및 사용 하는 방법에 대 한 정보를 제공 합니다. 범위를 벗어납니다도이 항목의 합니다. 이 항목에서는 시작 지점 고 여기서 참조 된 모든 Windows Api에 자세히 알아보려면 MSDN을 참조 하십시오.

## <a name="architecture-and-terminology"></a>아키텍처 및 용어

일반적으로 진단 도구에는 다음 그림에 표시 된 것 처럼 아키텍처입니다. "Profiler" 라는 용어를 사용 하지만 이러한 도구는 많은 일반적인 성능 또는 코드 검사와 같은 영역으로 메모리 프로 파일링을 뛰어넘는 모의 개체 프레임 워크, 디버깅, 모니터링 및 등의 응용 프로그램 시간 이동. 편의상이 항목에서는 프로파일러로 이러한 모든 도구를 계속 됩니다.

다음 용어는이 항목 전체에서 사용 됩니다.

**애플리케이션**

이것이 프로파일러 분석 하는 응용 프로그램입니다. 일반적으로이 응용 프로그램의 개발자는 이제 응용 프로그램을 사용 하 여 문제를 진단 하는 데, 프로파일러를 사용 합니다. 일반적으로이 응용 프로그램을 Windows 데스크톱 응용 프로그램을 수 있지만이 항목에서 검토 하 고 Windows 스토어 앱.

**Profiler DLL**

이것이 분석 되 고 응용 프로그램의 프로세스 공간으로 로드 하는 구성 요소입니다. 프로파일러 "에이전트를," 라고도 하며이 구성 요소를 구현 하는 [ICorProfilerCallback](icorprofilercallback-interface.md)[ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)(2, 3, 등) 인터페이스 및 소비를 [ ICorProfilerInfo](icorprofilerinfo-interface.md)(2, 3, 등) 및 잠재적으로 분석된 응용 프로그램에 대 한 데이터를 수집 하는 인터페이스 응용 프로그램의 동작의 측면을 수정 합니다.

**Profiler UI**

이것이 프로파일러 사용자 상호 작용 하는 데스크톱 응용 프로그램입니다. 이 사용자에 게 응용 프로그램 상태를 표시 및 분석된 응용 프로그램의 동작을 제어 하는 방법을 제공 하는 일을 담당 합니다. 이 구성 요소는 항상 프로 파일링 되 고 응용 프로그램의 프로세스 공간에서 별도 자체 프로세스 공간에서 실행 됩니다. Profiler UI의 "연결 트리거"는 호출 하는 과정으로 사용할 수도 있습니다는 [iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md) 프로파일러 DLL을 하지 않은 경우 Profiler DLL을 로드할 수 분석된 응용 프로그램이 방법 시작 시 로드 합니다.

> [!IMPORTANT]
> Profiler UI 컨트롤 및 Windows 스토어 앱에서 보고서를 사용 하는 경우에 Windows 데스크톱 응용 프로그램을이 상태로 유지 됩니다. 패키지 및 Windows 스토어에서 진단 도구를 제공 하는 일을 할 수 예상 하지도 마십시오. 도구는 Windows 스토어 앱이 수행할 수 없습니다, Profiler UI 내에 다양 한 작업을 수행 해야 합니다.

이 문서 전체에서 샘플 코드를 가정합니다.

- CLR 프로 파일링 API의 요구 사항에 따라 네이티브 DLL을 해야 하므로 Profiler DLL c + +로 작성 됩니다.

- Profiler UI는 C#으로 작성 됩니다. 이렇게 할 필요는 있지만 Profiler UI의 프로세스에 대 한 언어에 요구 사항 없이 이기 때문에 간결 하 고 간단한는 언어를 선택 하지 않는 이유?

### <a name="windows-rt-devices"></a>Windows RT 장치

Windows RT 장치는 상당히 잠겨 있습니다. 타사 프로파일러 단순히 로드할 수 없습니다 이러한 장치에서. 이 문서는 Windows 8 Pc에 중점을 둡니다.

## <a name="consuming-windows-runtime-apis"></a>Windows 런타임 Api를 사용합니다.

다음 섹션에서 설명 하는 시나리오의 숫자에 Profiler UI 데스크톱 응용 프로그램 일부 새로운 Windows 런타임 Api를 사용 해야 합니다. 데스크톱 응용 프로그램에서 사용할 수 있는 Windows 런타임 Api를 이해 하려면 설명서를 참조 하는 것이 좋습니다 하 고 있는지 여부를 동작 다른 경우 라고 데스크톱 응용 프로그램 및 Windows 스토어 앱입니다.

Profiler UI가 관리 되는 코드로 작성 하는 경우 몇 가지 단계를 쉽게 해당 Windows 런타임 Api를 사용 하도록 하기 위해 수행 해야 됩니다. 참조 된 [데스크톱 앱 및 Windows 런타임에 관리 되는](https://go.microsoft.com/fwlink/?LinkID=271858) 자세한 문서.

## <a name="loading-the-profiler-dll"></a>Profiler DLL를 로드합니다.

이 섹션에서는 Profiler UI Profiler DLL을 로드 하 여 Windows 스토어 앱을 발생 하는 방법을 설명 합니다. 이 섹션에서 설명한 코드 Profiler UI 데스크톱 앱에서 속하며 따라서 데스크톱 앱에 대 한 안전 하지만 Windows 스토어 앱 용 반드시 안전 하지 않은 Windows Api를 사용 하는 것입니다.

Profiler UI에는 두 가지 방법으로 응용 프로그램의 프로세스 공간에 로드 되도록 Profiler DLL 발생할 수 있습니다.

- 환경 변수를 통해 제어 하는 대로 응용 프로그램 시작 시

- 호출 하 여 시작 된 후 응용 프로그램에 연결 하 여 합니다 [iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md) 메서드.

시작-로드 하 고 Windows 스토어 앱을 사용 하 여 제대로 작동 하려면 Profiler DLL의 연결-로드에 첫 번째 장애물 중 하나를 시작 됩니다. 두 형태 모두 로드 하는 몇 가지 특별 한 고려 사항에서 공통, 사람과 시작 해 보겠습니다.

### <a name="common-considerations-for-startup-and-attach-loads"></a>시작에 대 한 일반적인 고려 사항 및 로드를 연결 합니다.

**Profiler DLL에 서명**

Windows Profiler DLL을 로드할 때 Profiler DLL 올바르게 서명 되었는지 확인 합니다. 그러지 않으면 기본적으로 로드가 실패 합니다. 여기에는 두 가지 방법이 있습니다.

- Profiler DLL의 서명을 확인 합니다.

- 설치 해야 개발자 라이선스는 Windows 8 컴퓨터에서 도구를 사용 하기 전에 사용자를 알립니다. 이렇게 하려면 자동으로 Visual Studio 또는 명령 프롬프트에서 수동으로. 자세한 내용은 [개발자 라이선스 가져오기](https://docs.microsoft.com/previous-versions/windows/apps/hh974578(v=win.10))합니다.

**파일 시스템 권한**

Windows 스토어 앱을 로드 하 고는 파일 시스템 위치에서 Profiler DLL을 실행할 수 있는 권한이 있어야 합니다. residesBy 기본적으로 Windows 스토어 앱에서 대부분의 디렉터리 및 Profiler DLL 로드 실패 한 시도에 대 한 이러한 권한이 없는 다음과 같은 모양의 Windows 응용 프로그램 이벤트 로그에 항목을 생성 합니다.

```Output
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].
```

일반적으로 Windows 스토어 앱만 액세스할 수 있습니다 제한 된 집합을 디스크에 위치 합니다. 각 Windows 스토어 앱에는 모든 Windows 스토어 앱에 액세스 권한이 부여 된 점에는 파일 시스템에 다른 몇 가지 영역 뿐만 아니라 자체 응용 프로그램 데이터 폴더 액세스할 수 있습니다. 모든 Windows 스토어 앱 읽기 및 권한이 기본적으로 실행 되므로 Profiler DLL 및 Program Files 또는 Program Files (x86)를 아래 위치에서 해당 종속성을 설치 하는 것이 좋습니다.

### <a name="startup-load"></a>시작 부하

일반적으로 데스크톱 앱에서 Profiler UI 프롬프트 Profiler DLL의 시작 부하 필요한 CLR 프로 파일링 API 환경 변수를 포함 하는 환경 블록을 초기화 하 여 (즉, `COR_PROFILER`하십시오 `COR_ENABLE_PROFILING`, 및 `COR_PROFILER_PATH`), 및 그런 다음 해당 환경 블록을 사용 하 여 새 프로세스를 만드는 중입니다. Windows 스토어 앱에도 마찬가지 했지만 메커니즘은 서로 다릅니다.

**관리자 권한으로 실행 안 함**

처리 하는 경우 Windows 스토어 앱 프로세스 B는 프로세스를 생성 하려고 하는 실행 되어야 합니다 중간 무결성에 수준 높은 무결성 수준 (즉, 승격 되지 않았습니다)에 없습니다. 즉, Profiler UI 중간 무결성 수준에서 실행 해야 하거나 Windows 스토어 앱 시작을 처리 하기 위해 중간 무결성 수준에서 다른 데스크톱 프로세스를 생성 해야 합니다.

**프로필에 Windows 스토어 앱을 선택합니다.**

첫째, 프로파일러 사용자는 Windows 스토어 앱 시작을 요청 해야 합니다. 데스크톱 앱에 대 한 파일 찾아보기 대화 상자를 표시는 아마도 및 사용자를 찾아.exe 파일을 선택 합니다. 하지만 Windows 스토어 앱은 서로 다르며 찾아보기 대화 상자를 사용 하 여은 적합 하지 않습니다. 대신, 사용자에서 선택 하려면 해당 사용자에 대해 설치 하는 Windows 스토어 앱의 목록을 표시 하는 것이 좋습니다.

사용할 수는 <xref:Windows.Management.Deployment.PackageManager> 이 목록을 생성 하는 클래스입니다. `PackageManager` 데스크톱 앱에 사용할 수 있는 Windows 런타임 클래스 이며 실제로 *만* 데스크톱 앱에 사용할 수 있습니다.

데스크톱 앱을 작성 하는 가상 Profiler UI에서 다음 코드 예제에서는 C# 를 사용 합니다 `PackageManager` Windows 앱의 목록을 생성 하려면:

```csharp
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();
PackageManager packageManager = new PackageManager();
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);
```

**사용자 지정 환경 블록 지정**

새 COM 인터페이스가 [IPackageDebugSettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings), 진단의 몇 가지 형태를 쉽게 수행할 수 있도록 Windows 스토어 앱의 실행 동작을 사용자 지정할 수 있습니다. 해당 메서드 중 하나 [EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging), 시작 되 면 Windows 스토어 앱에는 환경 블록을 전달할 수 있도록 자동 프로세스가 일시 중단 해제 하는 등 기타 유용한 효과 함께 합니다. 환경 블록을이 환경 변수를 지정 해야 하는 위치 이기 때문에 중요 (`COR_PROFILER`, `COR_ENABLE_PROFILING`, 및 `COR_PROFILER_PATH)`) 하는 데 clr Profiler DLL을 로드 합니다.

다음 코드 조각을 살펴봅니다.

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, debuggerCommandLine,
                                                                 (IntPtr)fixedEnvironmentPzz);
```

이해 해야 하는 항목의 몇 가지 있습니다.

- `packageFullName` 패키지에 대해 반복 하 고 클릭 한 다음 확인할 수 있습니다 `package.Id.FullName`합니다.

- `debuggerCommandLine` 약간 더 흥미롭습니다. 사용자 지정 환경 블록을 Windows 스토어 앱에 전달 하기 위해 간단한 더미 디버거를 직접 작성 해야 합니다. Windows 시작 Windows 스토어 앱을 일시 중단 되 고이 예제에서와 같은 명령줄을 사용 하 여 디버거를 시작 하 여 디버거를 연결 합니다.

    ```Output
    MyDummyDebugger.exe -p 1336 -tid 1424
    ```

     여기서 `-p 1336` 가지게 프로세스 ID 1336 Windows 스토어 앱 및 `-tid 1424` 스레드 ID 1424은 일시 중단 된 스레드를 의미 합니다. 더미 디버거 명령줄에서 ThreadID를 구문 분석 하 고 해당 스레드를 다시 시작 하 고 종료 됩니다.

     다음은 몇 가지 예제 이렇게 하려면 c + + 코드 (오류 검사를 추가 하도록 일!).

    ```cpp
    int wmain(int argc, wchar_t* argv[])
    {
        // …
        // Parse command line here
        // …

        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,
                                                                  FALSE /* bInheritHandle */, nThreadID);
        ResumeThread(hThread);
        CloseHandle(hThread);
        return 0;
    }
    ```

     진단 도구 설치의 일부로이 더미 디버거를 배포 하 고 다음이 디버거의에 대 한 경로 지정 해야 합니다 `debuggerCommandLine` 매개 변수입니다.

**Windows 스토어 앱 시작**

Windows 스토어 앱을 시작 하는 순간 마지막 도착 합니다. 이미이 작업을 직접 수행을 시도 했다면 사용한, 했을 수 있는 [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) Windows Store 앱 프로세스를 만드는 방법을 없습니다. 사용 해야 하는 대신 합니다 [IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) 메서드. 이 위해 실행 하는 Windows 스토어 앱의 앱 사용자 모델 ID를 가져오려면 해야 합니다. 즉, 약간 꼼꼼히 매니페스트를 통해 수행 해야 하며

패키지에 대해 반복 하는 동안 ("선택는 Windows 스토어 앱을 프로필"에서 참조를 [시작 부하](#startup-load) 이전 섹션), 현재 패키지의 매니페스트에 포함 된 응용 프로그램의 집합을 선택 하는 것이 좋습니다:

```csharp
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";

AppxPackaging.IStream manifestStream;
SHCreateStreamOnFileEx(
                    manifestPath,
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE
                    0,              // file creation attributes
                    false,          // fCreate
                    null,           // reserved
                    out manifestStream);

IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);

IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();
```

예, 하나의 패키지로 여러 응용 프로그램 수 및 각 응용 프로그램에는 자체 응용 프로그램 사용자 모델 ID가 있습니다. 따라서 사용자 프로필에는 응용 프로그램을 요청 하 고 해당 특정 응용 프로그램의 응용 프로그램 사용자 모델 ID를 가져오는 하려는:

```csharp
while (appsEnum.GetHasCurrent() != 0)
{
    IAppxManifestApplication app = appsEnum.GetCurrent();
    string appUserModelId = app.GetAppUserModelId();
    //...
}
```

마지막으로, 이제 Windows 스토어 앱을 시작 해야 합니다.

```csharp
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);
```

**DisableDebugging를 호출 해야 합니다.**

호출 하는 경우 [IPackageDebugSettings::EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging)를 호출 하 여 직접 후 정리 하는 약속을 수행 합니다 [IPackageDebugSettings::DisableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) 메서드를 수행 해야 통해 프로 파일링 세션의 경우.

### <a name="attach-load"></a>부하를 연결 합니다.

사용 하 여 Profiler UI를 이미 실행을 시작 하는 응용 프로그램에는 Profiler DLL 연결 하고자 [iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md)합니다. Windows 스토어 앱도 마찬가지입니다. 하지만 앞에서 설명한 일반적인 고려 사항 외에도 대상 Windows 스토어 앱을 일시 중단 되지 않습니다.

**EnableDebugging**

시작 부하와 마찬가지로 호출을 [IPackageDebugSettings::EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging) 메서드. 환경 블록을 전달 하는 데 필요 하지 않지만 다른 기능 중 하나가 필요 합니다: 자동 프로세스가 일시 중단을 사용 하지 않도록 설정 합니다. Profiler UI를 호출 하는 경우 그러지 [AttachProfiler](iclrprofiling-attachprofiler-method.md), 대상 Windows 스토어 앱을 일시 중단 될 수 있습니다. 사실이 가능성이 사용자가 이제 하면 Profiler UI 상호 작용 하 고 Windows 스토어 앱에서 사용자의 화면에 활성 상태가 아닙니다. 하는 경우 Windows 스토어 앱이 일시 중단 수는 없습니다에 응답 하 고 CLR Profiler DLL에 연결할를 보냅니다는 신호입니다.

따라서 다음과 같은 작업을 수행 하려는:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, null /* debuggerCommandLine */,
                                                                 IntPtr.Zero /* environment */);
```

디버거 명령줄 또는 환경 블록을 지정 하지 않는 점을 제외 하 고 시작 부하 사례에 대 한 확인은 같은 호출입니다.

**DisableDebugging**

늘 그렇듯이 이룰 [IPackageDebugSettings::DisableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) 프로 파일링 세션이 완료 되 면 합니다.

## <a name="running-inside-the-windows-store-app"></a>Windows 스토어 앱 내에서 실행

따라서 Windows 스토어 앱에서 Profiler DLL를 마지막으로 로드 했습니다. 축소 된 Profiler DLL를 Windows 스토어 앱에 필요한 다른 규칙에서 재생 하는 방법을 가르칠 수 해야, 이제 권한 허용 되는 Api 및 사용 하 여 실행 하는 방법을 포함 합니다.

### <a name="stick-to-the-windows-store-app-apis"></a>Windows 스토어 앱 Api에 집중

Windows API를 검색 한 후, 모든 API는 데스크톱 앱, Windows 스토어 앱 중 하나 또는 둘 다에 적용할 수 있는 것으로 문서화 합니다 알 수 있습니다. 예를 들어, 합니다 **요구 사항** 부분에 대 한 설명서를 [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) 함수는 데스크톱 응용 프로그램에 적용 되도록 나타냅니다. 반면 합니다 [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) 함수는 데스크톱 앱과 Windows 스토어 앱에 대해 사용할 수 있습니다.

Profiler DLL을 개발 하는 경우 Windows 스토어 앱을는 것 처럼 처리 하 고만 Windows 스토어 앱에 사용 가능한 것으로 문서화 된 Api를 사용 합니다. 종속성 분석 (예를 들어, 실행할 수 있습니다 `link /dump /imports` 감사 Profiler DLL에 대 한), 고 종속성은 확인 하지는 및 참조 문서를 검색 합니다. 대부분의 경우에 위반 단순히 안전으로 문서화 된 API의 최신 형식으로 대체 하 여 해결할 수 있습니다 (예를 들어 교체 [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) 사용 하 여 [ InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).

Profiler DLL에 데스크톱 앱의 경우에 적용 되는 일부 Api를 호출 하 고 아직 처럼 보이는 Profiler DLL이 Windows 스토어 앱 내에서 로드 될 때에 작동을 확인할 수 있습니다. Windows 스토어 앱 프로세스에 로드 될 때 Profiler DLL에서 Windows 스토어 앱의 사용에 대 한 문서화 되지 모든 API 사용 하 여 위험한 것을 고려해 야 합니다.

- 이러한 Api는 Windows 스토어 앱에서 실행 되는 고유한 컨텍스트에서 호출 될 때 작동 하도록 보장 되지 않습니다.

- 서로 다른 Windows 스토어 앱 프로세스 내에서 호출 하는 경우 이러한 Api 일관 되 게 작동 하지 않을 수 있습니다.

- 이러한 Api는 현재 버전의 Windows, Windows 스토어 앱에서 제대로 작동할 것 처럼 보일 수 있지만 중단 될 수 있습니다 또는 Windows의 이후 릴리스에서 사용할 수 없게 합니다.

에 모든 위반 문제를 해결 하 고 위험을 방지 하기 위해이 최선이입니다.

반드시 특정 API에 반드시 하는 Windows 스토어 앱에 적합 한 대체를 찾을 수 없습니다를 찾을 수 있습니다. 이러한 경우 최소한 합니다.

- 테스트, 테스트, living daylights 해당 API의 사용 현황 부족 합니다.

- API 수 갑자기 중단 되거나 사라지는 경우 호출 이해에서 Windows 스토어 내의 앱에서 향후 버전의 Windows. 이 간주 하지 않을 호환성 문제가 microsoft 및의 사용을 지 원하는 우선 순위를 되지 않습니다.

### <a name="reduced-permissions"></a>권한이 낮춰 진된

Windows 스토어 앱 사용 권한 데스크톱 앱에서 다른 모든 방법을 표시 하려면이 항목의 범위를 벗어나는 것입니다. 하지만 분명 동작이 달라 지므로 Profiler DLL (데스크톱 앱을 비교 하 여 Windows 스토어 앱을 로드) 하는 경우 모든 리소스에 액세스 하려고 할 때마다. 파일 시스템은 가장 일반적인 예입니다. 있지만 디스크에 지정된 된 Windows 스토어 앱에 액세스할 수 있는 몇 가지 배치 (참조 [파일 액세스 및 사용 권한 (Windows 런타임 앱](https://docs.microsoft.com/previous-versions/windows/apps/hh967755(v=win.10))), Profiler DLL 동일한 제한이 적용 됩니다. 코드를 철저히 테스트 합니다.

### <a name="inter-process-communication"></a>프로세스 간 통신

Profiler DLL (Windows 스토어 앱 프로세스 공간에 로드)이 문서의 시작 부분에서 다이어그램에 표시 된 것과 같이 사용자 고유의 사용자 지정 간 프로세스를 통해 Profiler UI (데스크톱 응용 프로그램을 별도 프로세스 공간에서 실행)를 사용 하 여 통신 해야 합니다. 통신 (IPC) 채널입니다. Profiler UI 해당 동작을 수정 하려면 Profiler DLL에 대 한 신호를 보냅니다 및 Profiler DLL 후 처리 하 고 프로파일러 사용자에 게 표시에 대 한 Profiler UI로 분석된 하는 Windows 스토어 앱에서 데이터를 보냅니다.

대부분의 프로파일러를 이런 방식이으로 작동 해야 합니다. Windows 스토어 앱에 Profiler DLL 로드 되 면 IPC 메커니즘을 선택 되지만 좀 더 제한적입니다. 예를 들어, 명명 된 파이프의 일부가 아닌 SDK, Windows 스토어 앱을 사용할 수 없습니다.

하지만 물론 파일이에서는 여전히 라도 제한적인된 방식으로 합니다. 이벤트를 사용할 수 있습니다.

**파일을 통해 통신합니다.**

대부분의 데이터가 가능성이 Profiler DLL 및 Profiler UI 간에 파일을 통해 전달 합니다. 키 파일 위치에 Profiler DLL (Windows 스토어 앱의 컨텍스트) 및 Profiler UI 읽기 및 쓰기 액세스를 선택 하는 것입니다. 예를 들어 임시 폴더 경로 Profiler DLL와 Profiler UI에 액세스할 수 있는 위치 이지만 다른 Windows 스토어 앱 패키지에 없습니다 (따라서 다른 Windows 스토어 앱 패키지에서 기록 정보 보호)에 액세스할 수 있습니다.

Profiler UI와 Profiler DLL 확인할 수 없습니다이 경로 독립적으로. Profiler UI, 현재 사용자에 대 한 설치 된 모든 패키지에 반복 하는 경우 (이전 코드 예제 참조)에 대 한 액세스를 가져옵니다는 `PackageId` 이 코드 조각과 유사한 코드를 사용 하 여 임시 폴더 경로 파생 될 수 있는 클래스입니다. (늘 그렇듯이 오류 검사는 생략 간략하게 표현 하기 위해.)

```csharp
// C# code for the Profiler UI.
ApplicationData appData =
    ApplicationDataManager.CreateForPackageFamily(
        packageId.FamilyName);

tempDir = appData.TemporaryFolder.Path;
```

Profiler DLL 수 기본적으로 동일한 작업을 수행 하는 한편, 수 있지만 더 간단 하 게 액세스할 합니다 <xref:Windows.Storage.ApplicationData> 를 사용 하 여 클래스를 [ApplicationData.Current](xref:Windows.Storage.ApplicationData.Current%2A) 속성입니다.

**이벤트를 통해 통신**

Profiler UI 및 Profiler DLL 간의 간단한 신호 의미 체계를 하려는 경우에 Windows 스토어 앱 뿐만 아니라 데스크톱 앱 내에서 이벤트를 사용할 수 있습니다.

Profiler DLL에서 호출 하면 합니다 [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) 원하는 이름을 사용 하 여 명명된 된 이벤트를 만드는 함수입니다. 예를 들어:

```cpp
// Profiler DLL in Windows Store app (C++).
CreateEventEx(
    NULL,  // Not inherited
    "MyNamedEvent"
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */
    EVENT_ALL_ACCESS);
```

Profiler UI는 다음 명명 된 이벤트는 Windows 스토어 앱의 네임 스페이스에서 찾을 해야 합니다. 예를 들어 Profiler UI 호출할 수 없습니다 [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), 이벤트 이름으로 지정

`AppContainerNamedObjects\<acSid>\MyNamedEvent`

`<acSid>` Windows 스토어 앱을 AppContainer SID입니다. 이 항목의 이전 섹션에는 현재 사용자에 대 한 설치 된 패키지를 반복 하는 방법을 보여 주었습니다. 해당 샘플 코드에서 packageId 얻을 수 있습니다. PackageId에서 가져올 수 있습니다는 `<acSid>` 다음과 비슷한 코드를 사용 하 여:

```csharp
IntPtr acPSID;
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);

string acSid;
ConvertSidToStringSid(acPSID, out acSid);

string acDir;
GetAppContainerFolderPath(acSid, out acDir);
```

### <a name="no-shutdown-notifications"></a>종료 알림 없음

내 Windows 스토어 앱을 실행할 때 Profiler DLL 중 하나에 의존 하지 않아야 [icorprofilercallback:: Shutdown](icorprofilercallback-shutdown-method.md) 심지어 [DllMain](/windows/desktop/Dlls/dllmain) (사용 하 여 `DLL_PROCESS_DETACH`) Profiler DLL에 알리기 위해 호출 되 고 Windows 스토어 앱을 종료 됩니다. 실제로 호출 되지 않는 하시면 됩니다. 지금까지 많은 Profiler Dll 이러한 알림을으로 사용한 편리한 위치 디스크, 파일을 닫고, 등 Profiler UI에 다시 알림을 보내는 캐시를 플러시합니다. 그러나 이제 Profiler DLL 약간 다르게 구성 해야 합니다.

Profiler DLL 때 로깅 정보가 있어야 합니다. 성능상의 이유로 메모리에서 정보를 일괄 처리 및 일부 임계값 지난 크기가 증가 함에 따라 일괄 처리를 디스크에 플러시하는 것이 좋습니다. 하지만 아직 디스크에 플러시된 정보 손실 될 수 있다는 가정 합니다. 이 임계값을 신중 하 게 선택 하는 것이 좋습니다 및 Profiler UI는 Profiler DLL에서 기록 된 불완전 한 정보를 사용 하 여 처리를 강화 해야 함을 의미 합니다.

## <a name="windows-runtime-metadata-files"></a>Windows 런타임 메타 데이터 파일

이 범위를 벗어납니다 세부 정보로 이동 하려면이 문서의 파일에 있는 Windows 런타임 메타 데이터 (WinMD). 이 섹션에서는 CLR 프로 파일링 API Profiler DLL을 분석 하는 Windows 스토어 앱에서 WinMD 파일을 로드할 때 반응 하는 방법으로 제한 됩니다.

### <a name="managed-and-non-managed-winmds"></a>관리 및 관리 되지 않는 Winmd

새 Windows 런타임 구성 요소 프로젝트를 만들려면 Visual Studio를 사용 하는 개발자, 하는 경우 해당 프로젝트의 빌드는 개발자가 작성 한 메타 데이터 (클래스, 인터페이스 등의 형식 설명)를 설명 하는 WinMD 파일을 생성 합니다. 이 프로젝트는 C# 또는 VB로 작성 된 관리 되는 언어 프로젝트를 하는 경우 WinMD 파일 또한 즉 개발자의 소스 코드에서 컴파일된 모든 IL을 포함 하는 해당 형식의 구현을 포함 합니다. 이러한 파일을 관리 되는 WinMD 파일 이라고 합니다. Windows 런타임 메타 데이터와 기본 구현이 모두 포함에 흥미로운 일입니다.

반면, 개발자가 c + + Windows 런타임 구성 요소 프로젝트를 만든, 해당 프로젝트의 빌드 메타 데이터만 포함 하는 WinMD 파일을 생성 및 구현을 별도 네이티브 DLL로 컴파일됩니다. 마찬가지로, Windows SDK에서 제공 되는 WinMD 파일 Windows의 일부로 제공 되는 별도 네이티브 Dll로 컴파일된 구현과 메타 데이터만 포함 합니다.

아래 정보는 메타 데이터만 포함 하는 관리 되지 않는 Winmd 메타 데이터 및 구현에 포함 하는 관리 되는 Winmd 모두에 적용 됩니다.

### <a name="winmd-files-look-like-clr-modules"></a>CLR 모듈 같이 WinMD 파일 표시

CLR 관련해 서 모든 WinMD 파일은 모듈입니다. 따라서 CLR 프로 파일링 API에는 WinMD 파일을 로드 하는 경우 Profiler DLL 및 해당 Moduleid를 동일 하 게 관리 되는 다른 모듈에에서 알려 줍니다.

Profiler DLL 호출 하 여 다른 모듈에서 WinMD 파일을 구분할 수는 [ICorProfilerInfo3::GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) 메서드 및 검사 합니다 `pdwModuleFlags` 출력에 대 한 매개 변수는 [COR_PRF_MODULE_WINDOWS_ 런타임](cor-prf-module-flags-enumeration.md) 플래그입니다. (설정은 ModuleID WinMD를 나타내는 경우에입니다.)

### <a name="reading-metadata-from-winmds"></a>Winmd에서 메타 데이터 읽기

일반 모듈 처럼 WinMD 파일을 통해 읽을 수 있는 메타 데이터를 포함 합니다 [메타 데이터 Api](../../../../docs/framework/unmanaged-api/metadata/index.md)합니다. 그러나 CLR 관리 코드에서 프로그래밍 및 WinMD 파일을 사용 하는 개발자는 더 자연 스러운 프로그래밍 경험을 그려볼 수 있도록 WinMD 파일을 읽을 때에 Windows 런타임 형식을.NET Framework 형식으로 매핑합니다. 이러한 매핑 중 몇 가지 예제를 참조 하세요 [.NET Framework 지원에 대 한 Windows 스토어 앱 및 Windows 런타임](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)합니다.

따라서 보기 프로파일러 받습니다 메타 데이터 Api를 사용 하는 경우: 원시 Windows 런타임 뷰 또는 매핑된.NET Framework 뷰?  답변:가 있습니다.

호출 하는 경우는 [icorprofilerinfo:: Getmodulemetadata](icorprofilerinfo-getmodulemetadata-method.md) 와 같은 메타 데이터 인터페이스를 가져오려면 WinMD 메서드 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)를 설정 하도록 선택할 수 있습니다 [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)에 `dwOpenFlags` 이 매핑을 해제 하려면 매개 변수입니다. 그렇지 않은 경우 기본적으로 매핑이 될 예정입니다. 일반적으로 프로파일러 계속 매핑을 사용 하도록 설정 되므로 Profiler DLL 가져옵니다 WinMD 메타 데이터 (예를 들어, 형식 이름)에서 문자열을 친숙 하 고 자연 스러운 프로파일러 사용자에 게 표시 됩니다.

### <a name="modifying-metadata-from-winmds"></a>Winmd 메타 데이터를 수정합니다.

Winmd에 대 한 메타 데이터를 수정 하는 것은 지원 되지 않습니다. 호출 하는 경우는 [icorprofilerinfo:: Getmodulemetadata](icorprofilerinfo-getmodulemetadata-method.md) WinMD에 대 한 메서드 파일 및 지정 [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 에 `dwOpenFlags` 매개 변수와 같은 쓰기 가능한 메타 데이터 인터페이스에 대 한 요청 또는 [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)하십시오 [GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) 실패 합니다. 이 해당 계측 (예: AssemblyRefs 또는 새 메서드 추가)를 지원 하기 위해 메타 데이터를 수정 해야 하는 IL 다시 쓰기 프로파일러에 특히 중요 합니다. 확인 해야 하므로 [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) 먼저 (이전 섹션에서 설명 함) 이러한 모듈에 쓰기 가능한 메타 데이터 인터페이스에 대 한 요청 하지 않도록 해야 합니다.

### <a name="resolving-assembly-references-with-winmds"></a>Winmd 사용 하 여 어셈블리 참조 확인

많은 프로파일러 계측 또는 형식 검사를 사용 하 여 지원 하기 위해 수동으로 메타 데이터 참조를 확인 해야 합니다. 이러한 프로파일러는 표준 어셈블리 참조 보다는 완전히 다른 방식으로 이러한 참조는 확인 하기 때문에 CLR에서 Winmd를 가리키는 어셈블리 참조를 확인 하는 방법을 알아야 합니다.

## <a name="memory-profilers"></a>메모리 프로파일러

관리 되는 힙과 가비지 수집기는 Windows 스토어 앱 및 데스크톱 앱에서 기본적으로 다른있지 않습니다. 그러나, 프로파일러 작성자에 주의 해야 하는 몇 가지 미묘한 차이가 있습니다.

### <a name="forcegc-creates-a-managed-thread"></a>ForceGC 관리 되는 스레드를 만듭니다.

Profiler DLL에서 일반적으로 호출 하는 별도 스레드를 만드는 메모리 프로 파일링 작업을 수행 하는 경우는 [ForceGC 메서드](icorprofilerinfo-forcegc-method.md) 메서드. 이것이 새로운 것입니다. Windows 스토어 앱 내에서 가비지 수집 작업을 수행 하는 작업 관리 되는 스레드를 스레드를 변환할 수 있는 다르다는 점에 놀라실 수도 있지만 (예를 들어, 프로 파일링 API ThreadID 만들어집니다 해당 스레드에 대 한).

가이 작업의 결과 이해 하려면 CLR 프로 파일링 API에 정의 된 동기 및 비동기 호출 간의 차이점을 이해 해야 합니다. 이 Windows 스토어 앱에 대 한 비동기 호출의 개념에서 매우 다른 note 합니다. 블로그 게시물을 참조 하세요 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE 있다고 이유](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) 자세한 내용은 합니다.

관련 된 중요 한 점은 프로파일러를 만든 스레드에서 호출 항상 간주 됩니다 동기적으로 호출 Profiler DLL의 하나의 구현 외부에서 만들어진 경우에 [ICorProfilerCallback](icorprofilercallback-interface.md) 메서드. 적어도 사용 되는 경우. CLR에 전환 프로파일러의 스레드 관리 되는 스레드를 호출 하 여 인해 했으므로 [ForceGC 메서드](icorprofilerinfo-forcegc-method.md), 스레드 프로파일러의 스레드도 인정 되지 않습니다. CLR로 해당 스레드에 대 한 동기의 요건은 무엇입니까 좀 더 엄격한 정의가 적용 하는 이와 같이-즉 호출에서 발생 해야 하는 Profiler DLL 중 하나의 내부 [ICorProfilerCallback](icorprofilercallback-interface.md) 메서드를 동기로 한정 합니다.

실제로 무슨 뜻인가요? 대부분 [ICorProfilerInfo](icorprofilerinfo-interface.md) 메서드 동기적으로 호출 되는 안전한 전용 이며 그렇지 않은 경우 즉시 실패 합니다. Profiler DLL을 다시 사용 하는 경우에 [ForceGC 메서드](icorprofilerinfo-forcegc-method.md) 프로파일러에서 생성 된 스레드의 일반적으로 한 다른 호출에 대 한 스레드 (예를 들어 [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](icorprofilerinfo4-requestrejit-method.md), 또는 [RequestRevert](icorprofilerinfo4-requestrevert-method.md)), 문제가 하려고 합니다. 와 같은 비동기 스레드로부터 안전한 함수 에서도 [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 에 관리 되는 스레드에서 호출 될 때 특별 한 규칙이 있습니다. (블로그 게시물을 참조 [Profiler stack walking: 기본 사항 이상](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) 자세한.)

따라서 좋습니다 Profiler DLL에서 호출 하기 위해 만드는 스레드 [ForceGC 메서드](icorprofilerinfo-forcegc-method.md) 사용할지 *만* Gc 트리거 하 고 다음 GC 콜백에 응답 하기 위해. 스택 샘플링 또는 분리와 같은 다른 작업을 수행 하는 프로 파일링 API를 호출 하지 않습니다.

### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

.NET Framework 4.5부터 새 GC 콜백을 [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md), 프로파일러에 대 한 정보를 더 완료 제공 *종속 핸들*합니다. 이러한 핸들은 효과적으로 GC 수명 관리 하기 위해 대상 개체에 원본 개체에서 참조를 추가합니다. 종속 핸들은 전혀 새로운, 및 관리 코드에서 프로그래밍 하는 개발자가 자신의 종속 핸들을 사용 하 여 만들 수 있는 여 <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> Windows 8 및.NET Framework 4.5 전이라 클래스입니다.

그러나 XAML Windows 스토어 앱 관리는 이제 종속 핸들의 과도 한 사용을 확인합니다. 특히 CLR 관리 되는 개체와 관리 되지 않는 Windows 런타임 개체 간의 참조 주기를 관리 하기 위해 사용 합니다. 이 보다 중요 해 졌 힙 그래프의에 지의 나머지 부분과 함께 시각화할 수 있도록 이러한 종속 핸들의 받아야 메모리 프로파일러에 대 한 어느 것을 의미 합니다. Profiler DLL을 사용할지 [RootReferences2](icorprofilercallback2-rootreferences2-method.md)하십시오 [ObjectReferences](icorprofilercallback-objectreferences-method.md), 및 [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) 힙 그래프의 한 전체 보기를 형성 하 .

## <a name="conclusion"></a>결론

CLR 프로 파일링 API를 사용 하 여 Windows 스토어 앱 내에서 실행 되는 관리 되는 코드를 분석 하는 것이 가능 합니다. 사실, 개발 중인 기존 프로파일러를 사용 하 고 Windows 스토어 앱이 대상으로 지정할 수 있도록 몇 가지 특정 변경할 수 있습니다. Profiler UI 디버깅 모드에서 Windows 스토어 앱을 활성화 하기 위한 새로운 Api를 사용 해야 합니다. Profiler DLL Windows 스토어 앱에 대 한 해당 Api만 사용 하 고 있는지 확인 합니다. Windows 스토어 앱 API 제한 사항을 염두에서에 Windows 스토어 앱에 대 한 제한 된 사용 권한 인식 Profiler UI 고 Profiler DLL 사이의 통신 메커니즘을 작성 되어야 합니다. Profiler DLL CLR Winmd를 처리 하는 방법을 알고 있어야 합니다. 가비지 수집기의 동작은 관리 되는 스레드 관련 하 여 다양 한 방법입니다.

## <a name="resources"></a>자료

**공용 언어 런타임**

- [프로 파일링 (관리 되지 않는 API 참조)](index.md)

- [메타 데이터 (관리 되지 않는 API 참조)](../metadata/index.md)

**Windows 런타임으로 CLR의 상호 작용**

- [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)

**Windows 스토어 앱**

- [파일 액세스 및 사용 권한 (Windows 런타임 앱](https://docs.microsoft.com/previous-versions/windows/apps/hh967755%28v=win.10%29)

- [개발자 라이선스 얻기](https://docs.microsoft.com/previous-versions/windows/apps/hh974578%28v=win.10%29)

- [IPackageDebugSettings 인터페이스](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings)
