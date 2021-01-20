---
title: Windows 10 마이그레이션
description: 패키징 및 XAML 아일랜드와 같은 Windows 10 기능에 대해 자세히 알아봅니다.
ms.date: 12/29/2020
ms.openlocfilehash: 139a8f2354803dafeb0178b4dbfb57a95c4ddb34
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615947"
---
# <a name="windows-10-migration"></a><span data-ttu-id="1aabf-103">Windows 10 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1aabf-103">Windows 10 migration</span></span>

<span data-ttu-id="1aabf-104">Windows 7 일 내에 개발 된 데스크톱 응용 프로그램을 사용 하는 경우를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1aabf-104">Consider the following situation: You have a working desktop application that was developed in the Windows 7 days.</span></span> <span data-ttu-id="1aabf-105">해당 시점에 사용할 수 있는 WPF 기술을 사용 하 고 정상적으로 작동 하지만, Windows 10에서 실행 하는 경우 오래 된 UI 및 동작을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-105">It's using WPF technology available at that time and working fine but it has an outdated UI and behaviors when you run it on Windows 10.</span></span> <span data-ttu-id="1aabf-106">행렬과 같은 futuristic 동영상을 시청 하는 경우와 Nokia 8110 장치를 사용 하는 Neo가 표시 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-106">It is like when you watch a futuristic movie like Matrix and you see Neo using the Nokia 8110 device.</span></span> <span data-ttu-id="1aabf-107">필름이 20 년 후에는 잘 작동 하지만 장치 현대화 혜택을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-107">The film works great after 20 years but it would rather benefit from a device modernization.</span></span>

<span data-ttu-id="1aabf-108">Microsoft는 Windows 10 릴리스부터 태블릿 및 터치 장치와 같은 시나리오를 지원 하 고 Microsoft 운영 체제의 사용자에 게 최상의 환경을 제공 하기 위해 많은 혁신을 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-108">With the release of Windows 10, Microsoft introduced many innovations to support scenarios like tablets and touch devices and to provide the best experience for users for a Microsoft operating system ever.</span></span> <span data-ttu-id="1aabf-109">예를 들어 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-109">For example, you can:</span></span>

- <span data-ttu-id="1aabf-110">Windows Hello를 사용 하 여 얼굴에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-110">Sign in with your face using Windows Hello.</span></span>
- <span data-ttu-id="1aabf-111">펜을 사용 하 여 자동으로 인식 되 고 digitalized 텍스트를 그리거나 필기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-111">Use a pen to draw or handwrite text that is automatically recognized and digitalized.</span></span>
- <span data-ttu-id="1aabf-112">WinML을 사용 하 여 클라우드에서 작성 된 로컬로 사용자 지정 된 AI 모델을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-112">Run locally customized AI models built on the cloud using WinML.</span></span>

<span data-ttu-id="1aabf-113">이러한 모든 기능은 Windows 개발자가 WinRT (Windows 런타임) 라이브러리를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-113">All these features are enabled for Windows developers through Windows Runtime (WinRT) libraries.</span></span> <span data-ttu-id="1aabf-114">라이브러리는 .NET Framework 및 .NET 모두에도 노출 되므로 기존 데스크톱 앱에서 이러한 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-114">You can take advantage of these features in your existing desktop apps because the libraries are exposed to both the .NET Framework and .NET as well.</span></span> <span data-ttu-id="1aabf-115">XAML 아일랜드를 사용 하 여 UI를 현대화 시간에 따라 앱의 시각적 개체 및 동작을 향상 시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-115">You can even modernize your UI with the use of XAML Islands and improve the visuals and behavior of your apps according to the times.</span></span>

<span data-ttu-id="1aabf-116">중요 한 한 가지 중요 한 점은이 현대화 경로를 따르기 위해 .NET Framework 기술을 중단 하지 않아도 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-116">One important thing to note here is that you don't need to abandon .NET Framework technology to follow this modernization path.</span></span> <span data-ttu-id="1aabf-117">안전 하 게 유지 하 고 .NET으로 마이그레이션하지 않고도 Windows 10의 모든 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-117">You can safely stay on there and have all the benefits of Windows 10 without the pressure to migrate to .NET.</span></span> <span data-ttu-id="1aabf-118">따라서 현대화 경로를 선택할 수 있는 기능과 유연성이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-118">So, you get both the power and the flexibility to choose your modernization path.</span></span>

## <a name="winrt-apis"></a><span data-ttu-id="1aabf-119">WinRT Api</span><span class="sxs-lookup"><span data-stu-id="1aabf-119">WinRT APIs</span></span>

<span data-ttu-id="1aabf-120">WinRT Api는 Windows 10 개발자가 운영 체제에서 제공 해야 하는 모든 항목에 액세스할 수 있게 해 주는 잘 구성 된 개체 지향 Api (응용 프로그래밍 인터페이스)입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-120">WinRT APIs are object-oriented, well-structured application programming interfaces (APIs) that give Windows 10 developers access to everything the operating system has to offer.</span></span> <span data-ttu-id="1aabf-121">WinRT Api를 통해 사용자 데스크톱 앱에서 푸시 알림, 장치 Api, Microsoft 잉크 및 WinML과 같은 기능을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-121">Through WinRT APIs, you can integrate functionalities like Push Notifications, Device APIs, Microsoft Ink, and WinML, among others on your desktop apps.</span></span>

<span data-ttu-id="1aabf-122">일반적으로 기존 데스크톱 앱에서 WinRT Api를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-122">In general, WinRT APIs can be called from a classic desktop app.</span></span> <span data-ttu-id="1aabf-123">그러나 두 가지 주요 영역에서이 규칙에 대 한 예외를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-123">However, two main areas present an exception to this rule:</span></span>

* <span data-ttu-id="1aabf-124">패키지 id를 필요로 하는 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-124">APIs that require a package identity.</span></span>
* <span data-ttu-id="1aabf-125">XAML 또는 컴퍼지션과 같은 시각화를 필요로 하는 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-125">APIs that require visualization like XAML or Composition.</span></span>

### <a name="universal-windows-platform-uwp-packages"></a><span data-ttu-id="1aabf-126">UWP (유니버설 Windows 플랫폼) 패키지</span><span class="sxs-lookup"><span data-stu-id="1aabf-126">Universal Windows Platform (UWP) packages</span></span>

#### <a name="application-package-identity"></a><span data-ttu-id="1aabf-127">응용 프로그램 패키지 Id</span><span class="sxs-lookup"><span data-stu-id="1aabf-127">Application Package Identity</span></span>

<span data-ttu-id="1aabf-128">UWP 앱에는 OS에서 응용 프로그램의 설치 및 제거를 관리 하는 배포 시스템이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-128">UWP apps have a deployment system where the OS manages the installation and uninstallation of application.</span></span> <span data-ttu-id="1aabf-129">이렇게 하면 설치 하는 동안 사용자 코드가 실행 되지 않는다는 의미의 설치를 선언형으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-129">That requires the installation to be declarative, meaning that no user code is executed during install.</span></span> <span data-ttu-id="1aabf-130">대신 응용 프로그램은 프로토콜, 파일 형식 및 확장과 같은 시스템과 통합 하려는 모든 항목을 응용 프로그램 매니페스트에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-130">Instead, everything the app wants to integrate with the system, such as protocols, file types, and extensions, is declared in the application manifest.</span></span> <span data-ttu-id="1aabf-131">배포 시 배포 파이프라인은 이러한 통합 요소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-131">At deployment time, the deployment pipeline configures those integration points.</span></span> <span data-ttu-id="1aabf-132">OS에서이 기능을 모두 관리 하 고 추적을 유지 하는 유일한 방법은 응용 프로그램에 대 한 고유 식별자 인 id를 각 ' 패키지 '에 포함 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-132">The only way for the OS to manage all this functionality and keep track of it is for each 'package' to have an identity, a unique identifier for the application.</span></span>

<span data-ttu-id="1aabf-133">일부 WinRT Api는이 패키지 id가 예상 대로 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-133">Some WinRT APIs require this package identity to work as expected.</span></span> <span data-ttu-id="1aabf-134">그러나 기본 c + + 또는 .NET 앱과 같은 클래식 데스크톱 앱은 패키지 id가 필요 없는 다른 배포 시스템을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-134">However, classic desktop apps like native C++ or .NET apps, use different deployment systems that don't require a package identity.</span></span> <span data-ttu-id="1aabf-135">데스크톱 응용 프로그램에서 이러한 WinRT Api를 사용 하려면 패키지 id를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-135">If you want to use these WinRT APIs in your desktop application, you need to provide them a package identity.</span></span>

<span data-ttu-id="1aabf-136">진행 하는 한 가지 방법은 추가 패키징 프로젝트를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-136">One way to proceed is to build an additional packaging project.</span></span> <span data-ttu-id="1aabf-137">패키징 프로젝트 내에서 원래 소스 코드 프로젝트를 가리키고 제공 하려는 Id 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-137">Inside the packaging project, you point to the original source code project and specify the Identity information you want to provide.</span></span> <span data-ttu-id="1aabf-138">패키지를 설치 하 고 설치 된 앱을 실행 하는 경우 코드에서 Id를 필요로 하는 모든 WinRT Api를 호출할 수 있도록 자동으로 식별을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-138">If you install the package and run the installed app, it will automatically get an identify enabling your code to call all WinRT APIs requiring Identity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10">
    <Identity Name="YOUR-APP-GUID "
              Publisher="CN=YOUR COMPANY"
              Version="1.x.x.x" />
</Package>
```

<span data-ttu-id="1aabf-139">API를 포함 하는 형식이 [DualApiPartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) 특성으로 표시 되어 있는지 검사 하 여 패키지 된 응용 프로그램 id가 필요한 api를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-139">You can check which APIs need a packaged application identity by inspecting if the type that contains the API is marked with the [DualApiPartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) attribute.</span></span> <span data-ttu-id="1aabf-140">인 경우 패키지 되지 않은 기존 데스크톱 앱에서를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-140">If it is, you can call if from an unpackaged traditional desktop app.</span></span> <span data-ttu-id="1aabf-141">그렇지 않으면 패키징 프로젝트의 도움을 사용 하 여 클래식 데스크톱 앱을 UWP로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-141">Otherwise, you must convert your classic desktop app to a UWP with the help of a packaging project.</span></span>

<https://docs.microsoft.com/windows/desktop/apiindex/uwp-apis-callable-from-a-classic-desktop-app>

#### <a name="benefits-of-packaging"></a><span data-ttu-id="1aabf-142">포장의 이점</span><span class="sxs-lookup"><span data-stu-id="1aabf-142">Benefits of packaging</span></span>

<span data-ttu-id="1aabf-143">이러한 Api에 대 한 액세스를 제공 하는 것 외에도 다음을 포함 하 여 데스크톱 응용 프로그램에 대 한 Windows 앱 패키지를 만들어 몇 가지 이점을 얻을 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="1aabf-143">Besides giving you access to these APIs, you get some additional benefits by creating a Windows App package for your desktop application including:</span></span>

* <span data-ttu-id="1aabf-144">**효율적인 배포**.</span><span class="sxs-lookup"><span data-stu-id="1aabf-144">**Streamlined deployment**.</span></span> <span data-ttu-id="1aabf-145">앱에는 사용자가 응용 프로그램을 안전 하 게 설치 하 고 업데이트할 수 있도록 하는 뛰어난 배포 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-145">Apps have a great deployment experience ensuring that users can confidently install an application and update it.</span></span> <span data-ttu-id="1aabf-146">사용자가 앱을 제거 하도록 선택 하는 경우 Windows rot 문제를 방지 하는 것이 남아 있는 추적 없이 완전히 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-146">If a user chooses to uninstall the app, it's removed completely with no trace left behind preventing the Windows rot problem.</span></span>

* <span data-ttu-id="1aabf-147">**자동 업데이트 및 라이선스**.</span><span class="sxs-lookup"><span data-stu-id="1aabf-147">**Automatic updates and licensing**.</span></span> <span data-ttu-id="1aabf-148">응용 프로그램은 Microsoft Store의 기본 제공 라이선스 및 자동 업데이트 기능에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-148">Your application can participate in the Microsoft Store's built-in licensing and automatic update facilities.</span></span> <span data-ttu-id="1aabf-149">자동 업데이트는 파일의 변경 된 부분만 다운로드 하므로 매우 안정적이 고 효율적인 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-149">Automatic update is a highly reliable and efficient mechanism, because only the changed parts of files are downloaded.</span></span>

* <span data-ttu-id="1aabf-150">**증가 된 도달 및 간소화 된 수익 화**.</span><span class="sxs-lookup"><span data-stu-id="1aabf-150">**Increased reach and simplified monetization**.</span></span> <span data-ttu-id="1aabf-151">사용자의 경우는 아니지만 Microsoft Store를 통해 응용 프로그램을 배포 하도록 선택 하는 경우 수백만 개의 Windows 10 사용자에 게 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-151">Maybe not your case but if you choose to distribute your application through the Microsoft Store you reach millions of Windows 10 users.</span></span>

* <span data-ttu-id="1aabf-152">**UWP 기능을 추가** 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-152">**Add UWP features**.</span></span> <span data-ttu-id="1aabf-153">사용자의 속도로 UWP 기능을 앱의 패키지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-153">You can add UWP features to your app's package at your own pace.</span></span>

#### <a name="prepare-for-packaging"></a><span data-ttu-id="1aabf-154">패키징 준비</span><span class="sxs-lookup"><span data-stu-id="1aabf-154">Prepare for packaging</span></span>

<span data-ttu-id="1aabf-155">데스크톱 응용 프로그램의 패키지를 계속 진행 하기 전에 프로세스를 시작 하기 전에 해결 해야 할 몇 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-155">Before proceeding to package your desktop application, there are some points you have to address before starting the process.</span></span> <span data-ttu-id="1aabf-156">응용 프로그램은 모든 Microsoft Store 규칙 및 정책을 준수 하 고 UWP 응용 프로그램 모델에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-156">Your application must respect any of the Microsoft Store rules and policies and run in the UWP application model.</span></span> <span data-ttu-id="1aabf-157">예를 들어 .NET Framework 4.6.2 이상에서 실행 해야 하 고 `HKEY_CURRENT_USER` 레지스트리 하이브에 쓰고 AppData 폴더가 사용자 특정 앱 로컬 위치에 가상화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-157">For example, it has to run on the .NET Framework 4.6.2 or later and writes to the `HKEY_CURRENT_USER` registry hive and the AppData folders will be virtualized to a user-specific app-local location.</span></span>

<span data-ttu-id="1aabf-158">패키징을 위한 디자인 목표는 다른 앱과의 호환성을 유지 하면서 응용 프로그램 상태를 시스템 상태와 분리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-158">The design goal for packaging is to separate the application state from system state while maintaining compatibility with other apps.</span></span> <span data-ttu-id="1aabf-159">Windows 10에서는 응용 프로그램을 UWP 패키지 내에 배치 하 여이 목표를 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-159">Windows 10 accomplishes this goal by placing the application inside a UWP package.</span></span> <span data-ttu-id="1aabf-160">패키지에서 제공 하는 응용 프로그램의 신뢰할 수 있고 깨끗 한 설치 및 제거 동작의 약속을 달성 하기 위해 런타임에 파일 시스템 및 레지스트리를 검색 하 고 이러한 변경 내용을 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-160">It detects and redirects some changes to the file system and registry at run time to fulfill the promise of a trusted and clean install and uninstall behavior of an application provided by packaging.</span></span>

<span data-ttu-id="1aabf-161">데스크톱 응용 프로그램에 대해 만드는 패키지는 응용 프로그램에 및에 대 한 쓰기에 적용 되는 경량 가상화가 있지만 샌드 박싱 되지 않는 데스크톱 전용 완전 신뢰 응용 프로그램입니다 `HKCU` `AppData` .</span><span class="sxs-lookup"><span data-stu-id="1aabf-161">Packages that you create for your desktop application are desktop-only, full-trust applications that aren't sandboxed, although there's lightweight virtualization applied to the app for writes to `HKCU` and `AppData`.</span></span> <span data-ttu-id="1aabf-162">이러한 가상화를 통해 클래식 데스크톱 응용 프로그램에서 수행 하는 것과 동일한 방식으로 다른 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-162">This virtualization allows them to interact with other apps the same way classic desktop applications do.</span></span>

##### <a name="installation"></a><span data-ttu-id="1aabf-163">설치</span><span class="sxs-lookup"><span data-stu-id="1aabf-163">Installation</span></span>

<span data-ttu-id="1aabf-164">앱 패키지는 ' 실행 파일 ' 이라는 이름의 *% ProgramFiles% \\ windowsapps \\ package_name* 아래에 설치 됩니다 `app_name.exe` .</span><span class="sxs-lookup"><span data-stu-id="1aabf-164">App packages are installed under *%ProgramFiles%\\WindowsApps\\package_name*, with the executable titled `app_name.exe`.</span></span> <span data-ttu-id="1aabf-165">각 패키지 폴더에는 `AppxManifest.xml` 패키지 된 앱에 대 한 특수 XML 네임 스페이스를 포함 하는 매니페스트 ()가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-165">Each package folder contains a manifest (named `AppxManifest.xml`) that contains a special XML namespace for packaged apps.</span></span> <span data-ttu-id="1aabf-166">해당 매니페스트 파일 내에는 `<EntryPoint>` 완전 신뢰 앱을 참조 하는 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-166">Inside that manifest file is an `<EntryPoint>` element, which references the full-trust app.</span></span> <span data-ttu-id="1aabf-167">응용 프로그램이 시작 되 면 앱 컨테이너 내에서 실행 되지 않고, 대신 일반적으로 사용자로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-167">When that application is launched, it doesn't run inside an app container, but instead it runs as the user as it normally would.</span></span>

<span data-ttu-id="1aabf-168">배포 후 패키지 파일은 운영 체제에 의해 읽기 전용으로 표시 되 고 매우 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-168">After deployment, package files are marked read-only and heavily locked down by the operating system.</span></span> <span data-ttu-id="1aabf-169">이러한 파일이 변조 되 면 Windows에서 앱을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-169">Windows prevents apps from launching if these files are tampered with.</span></span>

##### <a name="file-system"></a><span data-ttu-id="1aabf-170">파일 시스템</span><span class="sxs-lookup"><span data-stu-id="1aabf-170">File system</span></span>

<span data-ttu-id="1aabf-171">OS는 폴더 위치에 따라 패키지 된 데스크톱 응용 프로그램에 대해 서로 다른 수준의 파일 시스템 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-171">The OS supports different levels of file system operations for packaged desktop applications, depending on the folder location.</span></span>

<span data-ttu-id="1aabf-172">사용자의 *AppData* 폴더에 액세스 하려고 할 때 시스템은 백그라운드에서 사용자 단위, 앱 별 앱 위치를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-172">When trying to access the user's *AppData* folder, the system creates a private per-user, per-app location behind the scenes.</span></span> <span data-ttu-id="1aabf-173">이렇게 하면 패키지 응용 프로그램에서 실제로 개인 복사를 수정할 때 실제 *AppData* 을 편집 하는 것과 같은 환상 효과를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-173">This creates the illusion that the packaged application is editing the real *AppData* when it's actually modifying a private copy.</span></span> <span data-ttu-id="1aabf-174">시스템은 이러한 방식으로 쓰기를 리디렉션하여 앱에서 수행 하는 모든 파일 수정 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-174">By redirecting writes this way, the system can track all file modifications made by the app.</span></span> <span data-ttu-id="1aabf-175">그러면 시스템 "rot"를 제거 하 고 사용자에 게 더 나은 응용 프로그램 제거 환경을 제공할 때 이러한 모든 파일을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-175">It can then clean all those files when uninstalling reducing system "rot" and providing a better application removal experience for the user.</span></span>

##### <a name="registry"></a><span data-ttu-id="1aabf-176">레지스트리</span><span class="sxs-lookup"><span data-stu-id="1aabf-176">Registry</span></span>

<span data-ttu-id="1aabf-177">앱 패키지에는 실제 레지스트리에서와 동등한 논리적으로 사용 되는 레지스트리 .dat 파일이 포함 되어 있습니다. `HKLM\Software`</span><span class="sxs-lookup"><span data-stu-id="1aabf-177">App packages contain a registry.dat file, which serves as the logical equivalent of `HKLM\Software` in the real registry.</span></span> <span data-ttu-id="1aabf-178">런타임에이 가상 레지스트리는이 hive의 내용을 네이티브 시스템 hive에 병합 하 여 두 항목의 단일 뷰를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-178">At runtime, this virtual registry merges the contents of this hive into the native system hive to provide a singular view of both.</span></span>

<span data-ttu-id="1aabf-179">모든 쓰기는 패키지를 업그레이드 하는 동안 유지 되며 응용 프로그램을 제거 하는 경우에만 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-179">All writes are kept during package upgrade and only deleted when the application is uninstalled.</span></span>

##### <a name="uninstallation"></a><span data-ttu-id="1aabf-180">제거</span><span class="sxs-lookup"><span data-stu-id="1aabf-180">Uninstallation</span></span>

<span data-ttu-id="1aabf-181">사용자가 패키지를 제거 하면 아래에 있는 모든 파일 및 폴더가 `C:\Program Files\WindowsApps\package_name` 제거 되 고 AppData 또는 해당 프로세스 중에 캡처된 레지스트리에 리디렉션된 모든 파일이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-181">When the user uninstalls a package, all files and folders located under `C:\Program Files\WindowsApps\package_name` are removed, as well as any redirected writes to AppData or the registry that were captured during the process.</span></span>

<span data-ttu-id="1aabf-182">패키지 응용 프로그램에서 설치, 파일 액세스, 레지스트리 및 제거를 처리 하는 방법에 대 한 자세한 내용은을 참조 하십시오 <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes> .</span><span class="sxs-lookup"><span data-stu-id="1aabf-182">For details about how a packaged application handles installation, file access, registry, and uninstallation, see <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes>.</span></span>

<span data-ttu-id="1aabf-183">확인할 항목의 전체 목록을 가져올 수 있습니다 <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare> .</span><span class="sxs-lookup"><span data-stu-id="1aabf-183">You can get a complete list of things to check on <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare>.</span></span>

## <a name="how-to-add-winrt-apis-to-your-desktop-project"></a><span data-ttu-id="1aabf-184">데스크톱 프로젝트에 WinRT Api를 추가 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1aabf-184">How to add WinRT APIs to your desktop project</span></span>

<span data-ttu-id="1aabf-185">이 섹션에서는 기존 WPF 응용 프로그램에서 알림 메시지를 통합 하는 방법에 대 한 연습을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-185">In this section, you can find a walkthrough on how to integrate Toast Notifications in an existing WPF application.</span></span> <span data-ttu-id="1aabf-186">코드 관점에서 간단 하지만 전체 프로세스를 설명 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-186">Although it's simple from the code perspective, it helps illustrate the whole process.</span></span> <span data-ttu-id="1aabf-187">알림은 .NET 앱에서 사용할 수 있는 사용 가능한 여러 WinRT Api 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-187">Notifications are one of the many available WinRT APIs available that you can use in .NET app.</span></span> <span data-ttu-id="1aabf-188">이 경우 API에는 패키지 Id가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-188">In this case, the API requires a Package Identity.</span></span> <span data-ttu-id="1aabf-189">Api에 패키지 Id가 필요 하지 않은 경우이 프로세스는 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-189">This process is more straightforward if the APIs don't require Package Identity.</span></span>

<span data-ttu-id="1aabf-190">파일을 읽고 화면에 내용을 표시 하는 기존 WPF 샘플 앱을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-190">Let's take an existing WPF sample app that reads files and shows its contents on the screen.</span></span> <span data-ttu-id="1aabf-191">목표는 응용 프로그램이 시작 될 때 알림 메시지를 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-191">The goal is to display a Toast Notification when the application starts.</span></span>

![실행 중인 샘플 응용 프로그램의 스크린샷](./media/windows-migration/sample-application.png)

<span data-ttu-id="1aabf-193">먼저, 사용할 Windows 10 API에 패키지 Id가 필요한 지 여부에 대 한 다음 링크를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-193">First, you should check in the following link whether the Windows 10 API that you'll use requires a Package Identity:</span></span>

<https://docs.microsoft.com/windows/apps/desktop/modernize/desktop-to-uwp-supported-api>

<span data-ttu-id="1aabf-194">샘플은 <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> 패키지 id가 필요한 API를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-194">Our sample will use the <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> API that requires a packaged identity:</span></span>

![Microsoft 설명서의 알림 클래스](./media/windows-migration/notification-class-documentation.png)

<span data-ttu-id="1aabf-196">WinRT API에 액세스 하려면 NuGet 패키지에 대 한 참조를 추가 합니다 `Microsoft.Windows.SDK.Contracts` .이 패키지는 백그라운드에서 자동으로 수행 됩니다 (자세한 내용은 참조 <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/> ).</span><span class="sxs-lookup"><span data-stu-id="1aabf-196">To access the WinRT API, add a reference to the `Microsoft.Windows.SDK.Contracts` NuGet package and this package will do the magic behind the scenes (see details at <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/>).</span></span>

<span data-ttu-id="1aabf-197">이제 일부 코드를 추가 하기 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-197">You're now prepared to start adding some code.</span></span>

<span data-ttu-id="1aabf-198">`ShowToastNotification`응용 프로그램 시작 시 호출 되는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-198">Create a `ShowToastNotification` method that will be called on application startup.</span></span> <span data-ttu-id="1aabf-199">XML 패턴에서 알림 메시지를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-199">It just builds a toast notification from an XML pattern:</span></span>

```csharp
private void ShowNotification(string title, string content, string image)
{
    string xmlString = $@"<toast><visual><binding template = 'ToastGeneric'><text>{title}</text><text>{content}</text><image src=>'{image}'</image></binding></visual></toast>";
    XmlDocument toastXml = new XmlDocument();
    toastXml.LoadXml(xmlString);
    ToastNotification toast = new ToastNotification(toastXml);
    ToastNotificationManager.CreateToastNotifier().Show(toast);
}
```

<span data-ttu-id="1aabf-200">프로젝트에는 알림 API에 패키지 Id가 필요 하 고 제공 하지 않았기 때문에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-200">Although the project builds, there are errors because the Notifications API requires a Package Identity and you didn't provide it.</span></span> <span data-ttu-id="1aabf-201">솔루션에 Windows 패키징 프로젝트를 추가 하면 문제가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-201">Adding a Windows Packaging Project to the solution will fix the issue:</span></span>

![Visual Studio의 새 프로젝트 추가 대화 상자 스크린샷](./media/windows-migration/add-packaging-project.png)

<span data-ttu-id="1aabf-203">지원할 최소 Windows 버전 및 대상으로 지정할 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-203">Select the minimum Windows version you want to support and the version you're targeting.</span></span> <span data-ttu-id="1aabf-204">모든 WinRT Api가 모든 Windows 10 버전에서 지원 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-204">Not all the WinRT APIs are supported in all Windows 10 versions.</span></span> <span data-ttu-id="1aabf-205">각 Windows 10 업데이트는이 버전 에서만 사용할 수 있는 새 Api를 추가 합니다. 하위 수준 지원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-205">Each Windows 10 update adds new APIs that are only available from this version; down-level support isn't available.</span></span>

![최소 Windows 버전 선택](./media/windows-migration/select-versions.png)

<span data-ttu-id="1aabf-207">다음 단계는 프로젝트 참조를 추가 하 여 Windows 패키징 프로젝트에 WPF 응용 프로그램을 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-207">Next step is to add the WPF application to the Windows Packaging Project by adding a project reference:</span></span>

![Windows 패키징 프로젝트에 WPF 응용 프로그램 추가](./media/windows-migration/add-application.png)

![참조 관리자](./media/windows-migration/reference-manager.png)

<span data-ttu-id="1aabf-210">Windows 패키징 프로젝트는 여러 앱을 패키지할 수 있으므로 진입점을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-210">A Windows Packaging Project can package several apps so you should set which one is the Entry Point:</span></span>

![진입점 설정](./media/windows-migration/set-entry-point.png)

<span data-ttu-id="1aabf-212">다음 단계는 솔루션 구성에서 WPF 프로젝트를 시작 프로젝트로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-212">Next step is to set the WPF Project as the startup Project in the solution configuration.</span></span> <span data-ttu-id="1aabf-213">F5 키를 눌러 컴파일 및 작성 하 고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-213">You can press F5 to compile and build and see the results.</span></span>

![실행 중인 샘플 응용 프로그램 및 결과 표시](./media/windows-migration/sample-app-result.png)

<span data-ttu-id="1aabf-215">앱을 설치할 수 있도록 패키지를 생성 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-215">Let's generate the package so you can install your app.</span></span> <span data-ttu-id="1aabf-216">**스토어**  >  **앱 패키지 만들기** 를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-216">Right click on **Store** > **Create App Packages**.</span></span>

![앱 패키지 만들기 대화 상자](./media/windows-migration/create-app-packages.png)

<span data-ttu-id="1aabf-218">컴퓨터에서 앱을 배포 하려면 테스트용 로드 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-218">Select the sideloading option to deploy the app from your machine:</span></span>

![테스트용 로드 옵션 선택](./media/windows-migration/select-sideloading-option.png)

<span data-ttu-id="1aabf-220">앱의 응용 프로그램 아키텍처를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-220">Select the application architecture of your app:</span></span>

![응용 프로그램 아키텍처 선택](./media/windows-migration/select-app-architecture.png)

<span data-ttu-id="1aabf-222">마지막으로 **만들기** 를 클릭 하 여 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-222">Finally, create the package by clicking on **Create**.</span></span>

## <a name="xaml-islands"></a><span data-ttu-id="1aabf-223">XAML Islands</span><span class="sxs-lookup"><span data-stu-id="1aabf-223">XAML Islands</span></span>

<span data-ttu-id="1aabf-224">XAML 아일랜드는 Windows 데스크톱 개발자가 Windows Forms 및 WPF를 비롯 한 기존 Win32 응용 프로그램에서 UWP XAML 컨트롤을 사용할 수 있도록 하는 구성 요소 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-224">XAML Islands are a set of components that enable Windows desktop developers to use UWP XAML controls on their existing Win32 applications, including Windows Forms and WPF.</span></span>

![XAML 아일랜드의 구조](./media/windows-migration/xaml-islands.png)

<span data-ttu-id="1aabf-226">표준 컨트롤을 사용 하 여 Win32 앱을 이미지 하 고 현대적인 세계의 컨트롤을 포함 하는 UWP UI의 "아일랜드"로 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-226">You can image your Win32 app with your standard controls and among them an "island" of UWP UI containing controls from the modern world.</span></span> <span data-ttu-id="1aabf-227">이 개념은에서 콘텐츠를 표시 하는 웹 페이지에 iFrame을 포함 하는 것과 유사 합니다. `different page.`</span><span class="sxs-lookup"><span data-stu-id="1aabf-227">The concept is similar as having an iFrame inside a web page that shows content from a `different page.`</span></span>

<span data-ttu-id="1aabf-228">Windows 10 Api의 기능을 추가 하는 것 외에도 XAML 아일랜드를 사용 하 여 앱 내에 UWP XAML의 일부를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-228">Besides adding functionality from the Windows 10 APIs, you can add pieces of UWP XAML inside of your app using XAML Islands.</span></span>

<span data-ttu-id="1aabf-229">Windows 10 1903 업데이트에는 Win32 창에서 UWP XAML 콘텐츠 호스팅을 허용 하는 Api 집합이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-229">Windows 10 1903 update introduces a set of APIs that allows hosting UWP XAML content in Win32 windows.</span></span> <span data-ttu-id="1aabf-230">Windows 10 1903에서 실행 되는 앱에만 XAML 아일랜드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-230">Only apps running on Windows 10 1903 can use XAML Islands.</span></span>

### <a name="the-road-to-xaml-islands"></a><span data-ttu-id="1aabf-231">XAML로의 이동 제도</span><span class="sxs-lookup"><span data-stu-id="1aabf-231">The road to XAML Islands</span></span>

<span data-ttu-id="1aabf-232">Microsoft에서 Win32 앱 (Windows Forms, WPF 및 네이티브 Win32 앱)을 현대화 하는 프레임 워크로 WinRT Api를 도입 하는 경우 XAML 아일랜드가 2012에서 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-232">The road to XAML Islands started in 2012 when Microsoft introduced the WinRT APIs as a framework to modernize the Win32 apps (Windows Forms, WPF, and native Win32 apps).</span></span> <span data-ttu-id="1aabf-233">그러나 WinRT 내부의 새 UI 컨트롤은 새 응용 프로그램에 사용할 수 있었지만 기존 응용 프로그램에 대해서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-233">However, the new UI controls inside WinRT were available for new applications but not for existing ones.</span></span>

<span data-ttu-id="1aabf-234">2015에서는 Windows 10과 함께 UWP가 탄생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-234">In 2015, along with Windows 10, UWP was born.</span></span> <span data-ttu-id="1aabf-235">UWP를 사용 하면 XBox, Mobile, Desktop 등의 Windows 장치에서 작동 하는 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-235">UWP allows you to create apps that work across Windows devices like XBox, Mobile, and Desktop.</span></span> <span data-ttu-id="1aabf-236">1 년 후에 Microsoft는 데스크톱 브리지 (이전의 Project Centennial)를 발표 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-236">One year later, Microsoft announced Desktop Bridge (formerly known as Project Centennial).</span></span> <span data-ttu-id="1aabf-237">데스크톱 브리지는 개발자가 기존 Win32 앱을 Microsoft Store으로 가져올 수 있도록 하는 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-237">Desktop Bridge is a set of tools that allowed developers to bring their existing Win32 apps to the Microsoft Store.</span></span> <span data-ttu-id="1aabf-238">2017에 추가 기능이 추가 되어 개발자가 작업 센터의 라이브 타일 및 알림과 같은 새로운 Windows 10 Api를 활용 하는 Win32 앱을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-238">More capabilities were added in 2017, allowing developers to enhance their Win32 apps leveraging some of the new Windows 10 APIs, like live tiles and notifications on the action center.</span></span> <span data-ttu-id="1aabf-239">그러나 아직 새 UI 컨트롤은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-239">But still, no new UI controls.</span></span>

<span data-ttu-id="1aabf-240">빌드 2018에서 Microsoft는 개발자가 앱을 UWP로 완전히 마이그레이션하지 않고도 새 Windows 10 XAML 컨트롤을 현재 Win32 앱에 사용할 수 있는 방법을 발표 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-240">At Build 2018, Microsoft announced a way for developers to use the new Windows 10 XAML controls into their current Win32 apps, without fully migrating their apps to UWP.</span></span> <span data-ttu-id="1aabf-241">UWP XAML 아일랜드의 브랜드 였습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-241">It was branded as UWP XAML Islands.</span></span>

### <a name="how-it-works"></a><span data-ttu-id="1aabf-242">작동 방식</span><span class="sxs-lookup"><span data-stu-id="1aabf-242">How it works</span></span>

<span data-ttu-id="1aabf-243">Windows 10 1903 업데이트에는 몇 가지 XAML 호스팅 Api가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-243">The Windows 10 1903 update introduces several XAML hosting APIs.</span></span> <span data-ttu-id="1aabf-244">그 중 두 가지는 `WindowsXamlManager` 및 `DesktopWindowXamlSource` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-244">Two of them are `WindowsXamlManager` and `DesktopWindowXamlSource`.</span></span>

<span data-ttu-id="1aabf-245">`WindowsXamlManager`클래스는 UWP XAML 프레임 워크를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-245">The `WindowsXamlManager` class handles the UWP XAML Framework.</span></span> <span data-ttu-id="1aabf-246">해당 `InitializeForCurrentThread` 메서드는 Win32 응용 프로그램의 현재 스레드 내에서 UWP XAML 프레임 워크를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-246">Its `InitializeForCurrentThread` method loads the UWP XAML Framework inside the current thread of the Win32 app.</span></span>

<span data-ttu-id="1aabf-247">는 `DesktopWindowXamlSource` XAML 아일랜드 콘텐츠의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-247">The `DesktopWindowXamlSource` is the instance of your XAML Island content.</span></span> <span data-ttu-id="1aabf-248">이 클래스에는 `Content` 인스턴스화하고 설정 해야 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-248">It has the `Content` property, which you're responsible for instantiating and setting.</span></span> <span data-ttu-id="1aabf-249">는를 `DesktopWindowXamlSource` 렌더링 하 고 HWND에서 해당 입력을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-249">The `DesktopWindowXamlSource` renders and gets its input from an HWND.</span></span> <span data-ttu-id="1aabf-250">XAML 아일랜드를 연결할 다른 HWND를 알고 있어야 하며, 부모의 HWND 크기를 조정 하 고 위치를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-250">It needs to know to which other HWND it will attach the XAML Island's one, and you're responsible for sizing and positioning the parent's HWND.</span></span>

<span data-ttu-id="1aabf-251">WPF 또는 Windows Forms 개발자는 일반적으로 코드 내에서 HWND를 처리 하지 않으므로 HWND 포인터를 이해 하 고 처리 하 고 Win32 및 UWP 환경을 전달 하는 기본 연결을 처리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-251">WPF or Windows Forms developers don't usually deal with HWND inside their code, so it may be hard to understand and handle HWND pointers and the underlying wiring stuff to communicate Win32 and UWP worlds.</span></span>

#### <a name="the-xaml-islands-net-wrappers"></a><span data-ttu-id="1aabf-252">XAML 아일랜드 .NET 래퍼</span><span class="sxs-lookup"><span data-stu-id="1aabf-252">The XAML Islands .NET Wrappers</span></span>

<span data-ttu-id="1aabf-253">Windows 커뮤니티 도구 키트에는 XAML 아일랜드를 보다 쉽게 사용할 수 있도록 하는 WPF 또는 Windows Forms에 대 한 XAML 아일랜드 .NET 래퍼가 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-253">The Windows Community Toolkit has a set the XAML Islands .NET wrappers for WPF or Windows Forms that make easier to use XAML Islands.</span></span> <span data-ttu-id="1aabf-254">이러한 래퍼는 Hwnd, 포커스 관리 등을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-254">These wrappers manage the HWNDs, the focus management, among other things.</span></span> <span data-ttu-id="1aabf-255">Windows Forms 및 WPF 개발자는 이러한 래퍼를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-255">Windows Forms and WPF developers should use these wrappers.</span></span>

<span data-ttu-id="1aabf-256">Windows 커뮤니티 도구 키트는 래핑된 컨트롤과 호스트 컨트롤 이라는 두 가지 형식의 컨트롤을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-256">The Windows Community Toolkit offers two types of controls: Wrapped Controls and Hosting Controls.</span></span>

##### <a name="wrapped-controls"></a><span data-ttu-id="1aabf-257">래핑된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1aabf-257">Wrapped Controls</span></span>

<span data-ttu-id="1aabf-258">이러한 래핑된 컨트롤은 일부 UWP 컨트롤을 Windows Forms 또는 WPF 컨트롤로 래핑하고 해당 개발자에 대 한 UWP 개념을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-258">These wrapped controls wrap some UWP controls into Windows Forms or WPF controls, hiding UWP concepts for those developers.</span></span> <span data-ttu-id="1aabf-259">이러한 컨트롤은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-259">These controls are:</span></span>

* <span data-ttu-id="1aabf-260">웹 보기 및 WebViewCompatible</span><span class="sxs-lookup"><span data-stu-id="1aabf-260">WebView and WebViewCompatible</span></span>
* <span data-ttu-id="1aabf-261">InkCanvas 및 InkToolbar</span><span class="sxs-lookup"><span data-stu-id="1aabf-261">InkCanvas and InkToolbar</span></span>
* <span data-ttu-id="1aabf-262">MediaPlayerElement</span><span class="sxs-lookup"><span data-stu-id="1aabf-262">MediaPlayerElement</span></span>
* <span data-ttu-id="1aabf-263">MapControl</span><span class="sxs-lookup"><span data-stu-id="1aabf-263">MapControl</span></span>

<span data-ttu-id="1aabf-264">프로젝트에 패키지를 추가 하 고 `Microsoft.Toolkit.Wpf.UI.Controls` 네임 스페이스에 대 한 참조를 포함 한 다음 사용을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-264">Add the `Microsoft.Toolkit.Wpf.UI.Controls` package to your project, include the reference to the namespace, and start using them.</span></span>

```xml
<Window
        ...
        xmlns:uwpControls="clr-namespace:Microsoft.Toolkit.Wpf.UI.Controls;assembly=Microsoft.Toolkit.Wpf.UI.Controls">
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="\*"/>
    </Grid.RowDefinitions>
    <uwpControls:InkToolbar TargetInkCanvas="{x:Reference Name=inkCanvas}"/>
    <uwpControls:InkCanvas Grid.Row="1" x:Name="inkCanvas" />
</Grid>
```

##### <a name="hosting-controls"></a><span data-ttu-id="1aabf-265">컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="1aabf-265">Hosting controls</span></span>

<span data-ttu-id="1aabf-266">XAML 아일랜드의 강력한 기능을 사용 하면 대부분의 자사 컨트롤, 타사 컨트롤 및 UWP 용으로 개발 된 사용자 지정 컨트롤을 확장할 수 있습니다 .이 컨트롤은 모든 기능을 갖춘 UI를 사용 하 여 "아일랜드"로 Windows Forms 및 WPF에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-266">The power of XAML Islands extends to most first-party controls, third-party controls, and custom controls developed for UWP, which can be integrated into Windows Forms and WPF as "Islands" with fully functional UI.</span></span> <span data-ttu-id="1aabf-267">`WindowsXamlHost`WPF 및 Windows Forms에 대 한 컨트롤을 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-267">The `WindowsXamlHost` control for WPF and Windows Forms allows doing this.</span></span>

<span data-ttu-id="1aabf-268">예를 들어 `WindowsXamlHost` WPF에서 컨트롤을 사용 하려면 `Microsoft.Toolkit.Wpf.UI.XamlHost` Windows 커뮤니티 도구 키트에서 제공 하는 패키지에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-268">For example, to use the `WindowsXamlHost` control in WPF, add a reference to the `Microsoft.Toolkit.Wpf.UI.XamlHost` package provided by the Windows Community Toolkit.</span></span>

<span data-ttu-id="1aabf-269">을 `WindowsXamlHost` UI 코드에 배치한 후에는 로드 하려는 UWP 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-269">Once you've placed your `WindowsXamlHost` into your UI code, specify which UWP type you want to load.</span></span> <span data-ttu-id="1aabf-270">`Button`사용자 지정 UWP 컨트롤인 여러 다른 컨트롤로 구성 된 또는 보다 복잡 한 컨트롤 처럼 래핑된 컨트롤을 사용 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-270">You can choose to use a wrapped control like a `Button` or a more complex one composed by several different controls, which are a custom UWP control.</span></span>

<span data-ttu-id="1aabf-271">다음 예제에서는 UWP를 추가 하는 방법을 보여 줍니다 `Button` .</span><span class="sxs-lookup"><span data-stu-id="1aabf-271">The following example shows how to add a UWP `Button`:</span></span>

```xml
<Window
        ...
        xmlns:xamlhost="clr-namespace:Microsoft.Toolkit.Wpf.UI.XamlHost;assembly=Microsoft.Toolkit.Wpf.UI.XamlHost">

<xamlhost:WindowsXamlHost x:Name="myUwpButton"
                          InitialTypeName="Windows.UI.Xaml.Controls.Button" />
```

<span data-ttu-id="1aabf-272">이에 접근 하는 방법에 대 한 명확한 권장 사항이 있으므로 사용자 지정 복합 컨트롤을 포함 하는 하나 이상의 단일 XAML 아일랜드에는 하나의 컨트롤을 포함 하는 여러 개의 아일랜드를 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-272">There's a clear recommendation on how to approach this and it's better to have one single and bigger XAML Island containing a custom composite control than to have several islands with one control on each.</span></span>

<span data-ttu-id="1aabf-273">XAML의 핵심 기능 중 하나는 바인딩 이며 Win32 코드와 아일랜드 간에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-273">One of the core features of XAML is binding and it works between your Win32 code and the island.</span></span> <span data-ttu-id="1aabf-274">따라서 UWP를 사용 하 여 Win32를 바인딩할 수 있습니다 `Textbox` `Textbox` .</span><span class="sxs-lookup"><span data-stu-id="1aabf-274">So, you can bind, for instance, a Win32 `Textbox` with a UWP `Textbox`.</span></span> <span data-ttu-id="1aabf-275">고려해 야 할 중요 한 한 가지 사항은 이러한 바인딩이 UWP에서 Win32에 이르기까지 단방향 바인딩 이기 때문입니다. XAML 아일랜드 내에서를 업데이트 하는 경우에는 `Textbox` Win32 텍스트 상자가 업데이트 되지만 그 밖의 방법은 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-275">One important thing to consider is that these bindings are one-way bindings, from UWP to Win32, so if you update the `Textbox` inside the XAML Island the Win32 Textbox will be updated, but not the other way around.</span></span>

<span data-ttu-id="1aabf-276">XAML 아일랜드를 사용 하는 방법에 대 한 연습은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1aabf-276">To see a walkthrough about how to use XAML Islands, see:</span></span>

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-standard-control-with-xaml-islands>

#### <a name="adding-uwp-xaml-custom-controls"></a><span data-ttu-id="1aabf-277">UWP XAML 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="1aabf-277">Adding UWP XAML custom controls</span></span>

<span data-ttu-id="1aabf-278">XAML 사용자 지정 컨트롤은 사용자 또는 제 3 자가 만든 컨트롤 (또는 사용자 정의 컨트롤)입니다 (WinUI 2.x 컨트롤 포함).</span><span class="sxs-lookup"><span data-stu-id="1aabf-278">A XAML custom control is a control (or user control) created by you or by third parties (including WinUI 2.x controls).</span></span> <span data-ttu-id="1aabf-279">Windows Forms 또는 WPF 앱에서 사용자 지정 UWP 컨트롤을 호스트 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-279">To host a custom UWP control in a Windows Forms or WPF app, you'll need:</span></span>

- <span data-ttu-id="1aabf-280">`WindowsXamlHost`.Net 앱에서 UWP 컨트롤을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="1aabf-280">To use the `WindowsXamlHost` UWP control in your .NET app.</span></span>
- <span data-ttu-id="1aabf-281">개체를 정의 하는 UWP 앱 프로젝트를 만듭니다 `XamlApplication` .</span><span class="sxs-lookup"><span data-stu-id="1aabf-281">To create a UWP app project that defines a `XamlApplication` object.</span></span>

<span data-ttu-id="1aabf-282">WPF 또는 Windows Forms 프로젝트에 `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` 는 Windows 커뮤니티 도구 키트에서 제공 하는 클래스의 인스턴스에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-282">Your WPF or Windows Forms project must have access to an instance of the `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` class provided by the Windows Community Toolkit.</span></span> <span data-ttu-id="1aabf-283">이 개체는 응용 프로그램의 현재 디렉터리에 있는 어셈블리의 사용자 지정 UWP XAML 형식에 대 한 메타 데이터를 로드 하기 위한 루트 메타 데이터 공급자로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-283">This object acts as a root metadata provider for loading metadata for custom UWP XAML types in assemblies in the current directory of your application.</span></span> <span data-ttu-id="1aabf-284">이렇게 하려면 빈 앱 (유니버설 Windows) 프로젝트를 WPF 또는 Windows Forms 프로젝트와 동일한 솔루션에 추가 하 고이 프로젝트의 기본 App 클래스를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-284">The recommended way to do this is to add a Blank App (Universal Windows) project to the same solution as your WPF or Windows Forms project and revise the default App class in this project.</span></span>

<span data-ttu-id="1aabf-285">사용자 지정 UWP XAML 컨트롤은이 UWP 앱 또는 WPF 또는 Windows Forms 프로젝트와 동일한 솔루션에서 참조 하는 독립 UWP 클래스 라이브러리 프로젝트에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-285">The custom UWP XAML control can be included on this UWP app or in an independent UWP Class Library project that you reference in the same solution as your WPF or Windows Forms project.</span></span>

<span data-ttu-id="1aabf-286">자세한 단계별 프로세스 설명은 다음에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-286">You can check a detailed step-by-step process description at:</span></span>

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

#### <a name="the-windows-ui-library-winui-2"></a><span data-ttu-id="1aabf-287">Windows UI 라이브러리 (WinUI 2)</span><span class="sxs-lookup"><span data-stu-id="1aabf-287">The Windows UI Library (WinUI 2)</span></span>

<span data-ttu-id="1aabf-288">OS와 함께 제공 되는 수신함 Windows 10 컨트롤 외에도 동일한 UWP XAML 팀은 Windows UI 라이브러리 (**WinUI 2**)에서 추가 컨트롤을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-288">Besides the inbox Windows 10 controls that comes with the OS, the same UWP XAML team also deliver additional controls in the Windows UI Library (**WinUI 2**).</span></span> <span data-ttu-id="1aabf-289">WinUI 2는 Windows UWP 앱에 대 한 공식적인 네이티브 Microsoft UI 컨트롤 및 기능을 제공 하며, 이러한 컨트롤은 XAML 아일랜드 내에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-289">WinUI 2 provides official native Microsoft UI controls and features for Windows UWP apps and these controls can be used inside of XAML Islands.</span></span>

<span data-ttu-id="1aabf-290">WinUI 2는 오픈 소스 이며에서 정보를 찾을 수 있습니다 <https://github.com/microsoft/microsoft-ui-xaml> .</span><span class="sxs-lookup"><span data-stu-id="1aabf-290">WinUI 2 is open source and you can find information at <https://github.com/microsoft/microsoft-ui-xaml>.</span></span>

<span data-ttu-id="1aabf-291">다음 문서에서는 WinUI 2 라이브러리에서 UWP XAML 컨트롤을 호스트 하는 방법을 보여 줍니다. <https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands></span><span class="sxs-lookup"><span data-stu-id="1aabf-291">The following article demonstrates how to host a UWP XAML control from the WinUI 2 library: <https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands></span></span>

### <a name="do-you-need-xaml-islands"></a><span data-ttu-id="1aabf-292">XAML 아일랜드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-292">Do you need XAML Islands</span></span>

<span data-ttu-id="1aabf-293">XAML 아일랜드는 응용 프로그램을 완전히 다시 작성 하지 않고도 새 UWP 컨트롤 및 동작을 활용 하 여 사용자 환경을 개선 하고자 하는 기존 Win32 앱을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-293">XAML Islands are intended for existing Win32 apps that want to improve their user experience by leveraging new UWP controls and behaviors without a full rewrite of the app.</span></span> <span data-ttu-id="1aabf-294">[Windows 10 api](/windows/uwp/porting/desktop-to-uwp-enhance)를 이미 활용할 수 있지만 XAML 아일랜드 까지는 UI가 아닌 api를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-294">You could already [leverage Windows 10 APIs](/windows/uwp/porting/desktop-to-uwp-enhance), but up until XAML Islands, only non-UI related APIs.</span></span>

<span data-ttu-id="1aabf-295">새 Windows 앱을 개발 하는 경우 [UWP 앱](/windows/uwp/get-started/universal-application-platform-guide) 이 올바른 방법일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-295">If you're developing a new Windows App, a [UWP App](/windows/uwp/get-started/universal-application-platform-guide) is probably the right approach.</span></span>

### <a name="the-road-ahead-xaml-islands-winui-30"></a><span data-ttu-id="1aabf-296">XAML 아일랜드 앞으로 이동: WinUI 3.0</span><span class="sxs-lookup"><span data-stu-id="1aabf-296">The road ahead XAML Islands: WinUI 3.0</span></span>

<span data-ttu-id="1aabf-297">Windows 8부터 XAML UI 프레임 워크, 시각적 컴퍼지션 계층 및 입력 처리를 비롯 한 Windows UI 플랫폼은 Windows의 필수적인 부분으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-297">Since Windows 8, the Windows UI platform, including the XAML UI framework, visual composition layer, and input processing has been shipped as an integral part of Windows.</span></span> <span data-ttu-id="1aabf-298">즉, UI 기술의 최신 향상 기능을 활용 하려면 최신 버전의 UI로 업그레이드 하 여 앱을 개발할 때 혁신의 속도를 저하 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-298">This means that to benefit from the latest improvements on UI technologies, you must upgrade to the latest version of the UI, slowing down the pace of innovation when you develop your apps.</span></span> <span data-ttu-id="1aabf-299">이러한 두 가지 진화 주기를 분리 하 고 혁신을 촉진 하기 위해 Microsoft는 적극적으로 WinUI 프로젝트를 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-299">To decouple these two evolution cycles and foster innovation, Microsoft is actively working on the WinUI project.</span></span>

<span data-ttu-id="1aabf-300">2018에서 WinUI 2부터 Microsoft는 UWP SDK를 기반으로 구축 되는 별도의 NuGet 패키지로 몇 가지 새로운 XAML UI 컨트롤 및 기능을 출시 하기 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-300">Starting with WinUI 2 in 2018, Microsoft started shipping some new XAML UI controls and features as separate NuGet packages that build on top of the UWP SDK.</span></span>

![WinUI 2.0의 구조](./media/windows-migration/winui2.png)

<span data-ttu-id="1aabf-302">WinUI 3은 활성 개발 중 이며, 전체 UI 플랫폼을 포함 하도록 WinUI의 범위를 크게 확장 하며,이는 UWP SDK와 완전히 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-302">WinUI 3 is under active development and will greatly expand the scope of WinUI to include the full UI platform, which will be fully decoupled from the UWP SDK:</span></span>

![WinUI 3.0의 구조](./media/windows-migration/winui3.png)

<span data-ttu-id="1aabf-304">이제 GitHub에서 XAML 프레임 워크가 개발 되 고 [NuGet](/nuget/what-is-nuget) 패키지로 대역 외에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-304">XAML framework will now be developed on GitHub and shipped out of band as [NuGet](/nuget/what-is-nuget) packages.</span></span>

<span data-ttu-id="1aabf-305">OS의 일부로 제공되는 기존 UWP XAML API는 더 이상 새로운 기능 업데이트를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-305">The existing UWP XAML APIs that ship as part of the OS will no longer receive new feature updates.</span></span> <span data-ttu-id="1aabf-306">Windows 10 지원 주기에 따라 보안 업데이트 및 중요 한 수정이 계속 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-306">They will still receive security updates and critical fixes according to the Windows 10 support lifecycle.</span></span>

<span data-ttu-id="1aabf-307">유니버설 Windows 플랫폼에는 XAML 프레임 워크 (예: 응용 프로그램 및 보안 모델, 미디어 파이프라인, Xbox 및 Windows 10 shell 통합, 광범위 한 장치 지원)가 포함 되며 계속 해 서 진화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-307">The Universal Windows Platform contains more than just the XAML framework (for example, application and security model, media pipeline, Xbox and Windows 10 shell integrations, broad device support) and will continue to evolve.</span></span> <span data-ttu-id="1aabf-308">모든 새 XAML 기능이 개발 되 고 대신 WinUI의 일부로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-308">All new XAML features will just be developed and ship as part of WinUI instead.</span></span>

#### <a name="winui-3-in-desktop-app-and-winui-xaml-islands"></a><span data-ttu-id="1aabf-309">WinUI 3 (데스크톱 앱 및 WinUI XAML 제도)</span><span class="sxs-lookup"><span data-stu-id="1aabf-309">WinUI 3 in desktop app and WinUI XAML Islands</span></span>

<span data-ttu-id="1aabf-310">여기서 볼 수 있듯이 WinUI 3은 UWP XAML의 진화 이며 UWP 앱 모델 및 해당 요구 사항 (MSIX 패키지 ID, 샌드박스, CoreWindow 등) 내에서 자연스럽 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-310">As you can see, WinUI 3 is the evolution of UWP XAML and it works naturally within the UWP app model and all its requirements (MSIX packaged ID, sandbox, CoreWindow, and so on.</span></span> <span data-ttu-id="1aabf-311">WinUI 3을 Win32 앱 모델에서 사용 하려면 WinUI 콘텐츠를 **WINUI XAML 아일랜드** 를 사용 하는 다른 UI 프레임 워크 (WINDOWS FORMS, WPF 등)에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-311">To use just WinUI 3 in a Win32 app model, the WinUI content should be hosted by another UI Framework (Windows Forms, WPF, and so on) using **WinUI XAML Islands**.</span></span> <span data-ttu-id="1aabf-312">앱을 개선 하 고 기술을 혼합 하려는 경우 적합 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-312">This is the right path if you want to evolve your app and mix technologies.</span></span> <span data-ttu-id="1aabf-313">그러나 WinUI에 대 한 전체 이전 UI를 대체 하려는 경우 응용 프로그램에서 WinUI 호스트에 대 한 UI 프레임 워크를 로드 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-313">However, if you want to replace your entire old UI for WinUI, your app shouldn't load UI Frameworks for just hosting WinUI.</span></span>

<span data-ttu-id="1aabf-314">WinUI 3은 **데스크톱 앱에서 WinUI를** 추가 하는이 중요 한 피드백을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-314">WinUI 3 will address this critical feedback adding **WinUI in desktop apps**.</span></span> <span data-ttu-id="1aabf-315">이렇게 하면 Win32 앱이 독립 실행형 UI 프레임 워크로 WinUI 3을 사용할 수 있습니다. Windows Forms 또는 WPF를 로드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-315">This will allow that Win32 apps can use WinUI 3 as standalone UI Framework; no need to load Windows Forms or WPF.</span></span>

<span data-ttu-id="1aabf-316">이 집계 내에서 WinUI 3을 통해 개발자는 다음의 오른쪽 조합을 쉽게 조합 하 고 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-316">Within this aggregation, WinUI 3 will let developers easily mix and match the right combination of:</span></span>

* <span data-ttu-id="1aabf-317">앱 모델: UWP, Win32</span><span class="sxs-lookup"><span data-stu-id="1aabf-317">App model: UWP, Win32</span></span>
* <span data-ttu-id="1aabf-318">플랫폼: .NET 또는 네이티브</span><span class="sxs-lookup"><span data-stu-id="1aabf-318">Platform: .NET or Native</span></span>
* <span data-ttu-id="1aabf-319">언어: .NET (C \# , Visual Basic), 표준 c + +</span><span class="sxs-lookup"><span data-stu-id="1aabf-319">Language: .NET (C\#, Visual Basic), standard C++</span></span>
* <span data-ttu-id="1aabf-320">패키징: MSIX, Microsoft Store에 대 한 AppX, 패키지 되지 않은</span><span class="sxs-lookup"><span data-stu-id="1aabf-320">Packaging: MSIX, AppX for the Microsoft Store, unpackaged</span></span>
* <span data-ttu-id="1aabf-321">Interop: WinUI 3을 사용 하 여 WinUI XAML 아일랜드를 사용 하는 기존 WPF, WinForms 및 MFC 앱을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aabf-321">Interop: use WinUI 3 to extend existing WPF, WinForms, and MFC apps using WinUI XAML Islands.</span></span>

<span data-ttu-id="1aabf-322">자세한 정보를 확인 하려는 경우 Microsoft는에서이 로드맵을 공유 하 고 있습니다 <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md> .</span><span class="sxs-lookup"><span data-stu-id="1aabf-322">If you want to know more details, Microsoft is sharing this roadmap in <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1aabf-323">[이전](migrate-modern-applications.md)
>[다음](example-migration.md)</span><span class="sxs-lookup"><span data-stu-id="1aabf-323">[Previous](migrate-modern-applications.md)
[Next](example-migration.md)</span></span>
