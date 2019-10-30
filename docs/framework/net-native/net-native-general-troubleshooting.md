---
title: .NET 네이티브 일반 문제 해결
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
ms.openlocfilehash: 2bea81e380fed6c456898e9883658ef874c8dd97
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128235"
---
# <a name="net-native-general-troubleshooting"></a><span data-ttu-id="3740d-102">.NET 네이티브 일반 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3740d-102">.NET Native General Troubleshooting</span></span>

<span data-ttu-id="3740d-103">이 항목에서는 .NET 네이티브를 사용 하 여 앱을 개발할 때 발생할 수 있는 잠재적인 문제를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-103">This topic describes how to troubleshoot potential issues that you might encounter when developing apps with .NET Native.</span></span>

- <span data-ttu-id="3740d-104">**문제:** 빌드 출력 창이 제대로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-104">**Issue:** Your build output window isn't properly updated.</span></span>

  <span data-ttu-id="3740d-105">**해결 방법:** 빌드 출력 창은 빌드가 완료될 때까지 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-105">**Resolution:** The build output window isn't updated until the build completes.</span></span> <span data-ttu-id="3740d-106">빌드 시간은 몇 분까지 걸릴 수 있으므로 업데이트 표시가 다소 지연될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-106">Build times may be up to several minutes, so you might experience a delay in seeing the updates.</span></span>

- <span data-ttu-id="3740d-107">**문제:** ARM의 앱 정품 빌드 시간이 길어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-107">**Issue:** Your app’s retail build time for ARM has increased.</span></span>

  <span data-ttu-id="3740d-108">**해결 방법:** ARM 장치에 앱을 배포 하는 경우 .NET 네이티브 인프라가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-108">**Resolution:** When you deploy an app to your ARM device, the .NET Native infrastructure is invoked.</span></span> <span data-ttu-id="3740d-109">이 컴파일에서는 리플렉션 등의 정적이 아닌 의미 체계가 계속 작동하도록 하는 동시에 많은 최적화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-109">This compilation performs a large number of optimizations while ensuring that non-static semantics such as reflection continue to work.</span></span> <span data-ttu-id="3740d-110">또한 성능을 최적화하기 위해 앱이 사용하는 .NET Framework 부분이 정적으로 연결되며, 이 부분 역시 네이티브 코드로 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-110">In addition, the portion of the .NET Framework that the app uses is statically linked in for optimal performance and has to be compiled into native code as well.</span></span> <span data-ttu-id="3740d-111">이로 인해 컴파일 시간이 더 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-111">This is why compilation takes longer.</span></span>

  <span data-ttu-id="3740d-112">그러나 표준 개발 컴퓨터에서 대다수 앱의 표준 컴파일에 소요되는 컴파일 시간은 여전히 1분 이내입니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-112">However, compilation times are still within a minute of standard compilation for most apps on a standard development machine.</span></span>  <span data-ttu-id="3740d-113">일반적으로 표준 개발 컴퓨터에서 .NET Framework용 네이티브 이미지를 생성하는 작업만 수행해도 몇 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-113">Typically, just generating native images for the .NET Framework on a standard development machine takes several minutes.</span></span>  <span data-ttu-id="3740d-114">반면 생성된 코드를 개선하는 모든 최적화 작업과 .NET Framework 부분 컴파일 작업 시간을 모두 포함하더라도 앱 빌드 시간은 대개 1~2분에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-114">Even with all the optimizations to improve the generated code and with including the .NET Framework, app build times are typically a minute or two.</span></span>

  <span data-ttu-id="3740d-115">Microsoft는 다중 스레드 컴파일 및 기타 최적화를 조사하여 컴파일 성능을 개선하기 위해 지속적으로 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-115">We are continuing to work on improving compilation performance by investigating multi-threaded compilation and other optimizations.</span></span>

- <span data-ttu-id="3740d-116">**문제:** .NET 네이티브를 사용 하 여 앱을 컴파일 했는지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-116">**Issue:** You don’t know if your app was compiled using .NET Native.</span></span>

  <span data-ttu-id="3740d-117">**해결 방법:** .NET 네이티브 컴파일러를 호출 하면 빌드 시간이 길어질 수 있으며, 작업 관리자는 ILC 및 nutc_driver와 같은 다양 한 .NET 네이티브 구성 요소 프로세스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-117">**Resolution:** If the .NET Native compiler is invoked, you'll notice longer build times, and Task Manager will show various .NET Native component processes such as ILC.exe and nutc_driver.exe.</span></span>

  <span data-ttu-id="3740d-118">.NET 네이티브를 사용 하 여 프로젝트를 성공적으로 빌드한 후에는 .obj\\*구성*\ *아치*\\*projectname*. ilc\out.에서 출력을 찾을 수 있습니다.  최종 네이티브 패키지 내용은 bin\\*아치*\\*config*\appx에서 확인할에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-118">After you successfully build your project with .NET Native, you'll find the output under obj\\*config*\ *arch*\\*projectname*.ilc\out.  The final native package contents can be found under bin\\*arch*\\*config*\AppX.</span></span> <span data-ttu-id="3740d-119">앱을 배포한 경우 최종 네이티브 패키지 콘텐츠는 \bin\\*arch*\\*config*\AppX에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-119">The final native package contents are under \bin\\*arch*\\*config*\AppX if you have deployed the app.</span></span>

- <span data-ttu-id="3740d-120">**문제:** .NET 네이티브를 사용해서 컴파일한 앱에서 .NET 네이티브 없이 컴파일했을 때는 throw하지 않던 런타임 예외(일반적으로 [MissingMetadataException](missingmetadataexception-class-net-native.md) 또는 [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) 예외)를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-120">**Issue:** Your .NET Native-compiled app is throwing runtime exceptions (typically [MissingMetadataException](missingmetadataexception-class-net-native.md) or [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions) that it did not throw when compiled without .NET Native.</span></span>

  <span data-ttu-id="3740d-121">**해결 방법:** .NET 네이티브가 리플렉션을 통해 사용할 수 있는 구현 코드 또는 메타데이터를 제공하지 않았기 때문에 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-121">**Resolution:** The exceptions are thrown because .NET Native did not provide either the metadata or the implementation code that is otherwise available through reflection.</span></span> <span data-ttu-id="3740d-122">자세한 내용은 [.NET 네이티브 및 컴파일](net-native-and-compilation.md)을 참조 하세요. 예외를 제거 하려면 런타임 [지시문 (rd .xml) 파일](runtime-directives-rd-xml-configuration-file-reference.md) 에 항목을 추가 하 여 .NET 네이티브 도구 체인이 런타임에 메타 데이터 또는 구현 코드를 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-122">(For more information, see [.NET Native and Compilation](net-native-and-compilation.md).) To eliminate the exception, you have to add an entry to your [runtime directives (rd.xml) file](runtime-directives-rd-xml-configuration-file-reference.md) so that the .NET Native tool chain can make the metadata or implementation code available at runtime.</span></span> <span data-ttu-id="3740d-123">런타임 지시문 파일에 추가할 필수 항목을 생성하는 데 두 가지 문제 해결사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-123">Two troubleshooters are available that will generate the necessary entry to add to your runtime directives file:</span></span>

  - <span data-ttu-id="3740d-124">형식의 경우 [MissingMetadataException 문제 해결사](https://dotnet.github.io/native/troubleshooter/type.html) 입니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-124">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>

  - <span data-ttu-id="3740d-125">메서드의 경우 [MissingMetadataException 문제 해결사](https://dotnet.github.io/native/troubleshooter/method.html) 입니다.</span><span class="sxs-lookup"><span data-stu-id="3740d-125">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>

  <span data-ttu-id="3740d-126">자세한 내용은 [리플렉션 및 .NET 네이티브](reflection-and-net-native.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3740d-126">For more information, see [Reflection and .NET Native](reflection-and-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3740d-127">참조</span><span class="sxs-lookup"><span data-stu-id="3740d-127">See also</span></span>

- [<span data-ttu-id="3740d-128">Windows 스토어 앱을 .NET 네이티브로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3740d-128">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)
