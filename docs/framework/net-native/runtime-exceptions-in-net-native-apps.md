---
title: .NET 네이티브 앱의 런타임 예외
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
ms.openlocfilehash: 12df2ef7bf6e86a60dfa4c130f35969e72ac5211
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180945"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="bb511-102">.NET 네이티브 앱의 런타임 예외</span><span class="sxs-lookup"><span data-stu-id="bb511-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="bb511-103">디버그 및 릴리스 구성이 완전히 다르므로 해당 대상 플랫폼에서 유니버설 Windows 플랫폼 앱의 릴리스 빌드를 테스트하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="bb511-104">기본적으로 디버그 구성에서는 .NET 핵심 런타임을 사용하여 앱을 컴파일하지만 릴리스 구성에서는 .NET 네이티브를 사용하여 앱을 네이티브 코드로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bb511-105">앱의 릴리스 버전을 테스트할 때 발생할 수 있는 [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)및 [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) 예외를 처리 하는 방법에 대 한 자세한 내용은 [시작](getting-started-with-net-native.md) 항목의 "4 단계: 수동으로 누락 된 메타 데이터 문제 해결: [리플렉션 및 .NET 네이티브](reflection-and-net-native.md) 및 [런타임 지시문 (rd .xml) 구성 파일 참조](runtime-directives-rd-xml-configuration-file-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb511-105">For information on dealing with the [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see "Step 4: Manually resolve missing metadata: in the [Getting Started](getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="bb511-106">디버그 및 릴리스 빌드</span><span class="sxs-lookup"><span data-stu-id="bb511-106">Debug and release builds</span></span>  
 <span data-ttu-id="bb511-107">디버그 빌드가 .NET 핵심 런타임에 대해 실행될 때 네이티브 코드로 컴파일되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="bb511-108">그러므로 일반적으로 모든 서비스가 앱에서 사용 가능한 런타임에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="bb511-109">반면, 릴리스 빌드는 해당 대상 플랫폼을 위해 네이티브 코드로 컴파일되고, 외부 런타임 및 라이브러리의 종속성이 대부분 제거되고, 최대 성능을 위해 코드를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="bb511-110">.NET 네이티브를 사용하여 컴파일된 릴리스 빌드를 디버깅하는 경우:</span><span class="sxs-lookup"><span data-stu-id="bb511-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="bb511-111">기본 .NET 디버깅 도구와는 다른 .NET 네이티브 디버그 엔진을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="bb511-112">실행 파일의 크기가 가능한 만큼 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="bb511-113">.NET 네이티브에서 실행 파일의 크기를 줄이는 방법 중 하나는 런타임 예외 메시지를 크게 잘라내는 것입니다. 자세한 내용은 [Runtime exception messages](#Messages) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb511-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="bb511-114">코드가 매우 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-114">Your code is heavily optimized.</span></span> <span data-ttu-id="bb511-115">이는 가능할 때마다 인라인 처리가 사용된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="bb511-116">인라인 코드를 외부 루틴에서 호출 루틴으로 이동 합니다.   .NET 네이티브는 특수 런타임을 제공 하 고 적극적인 인라인을 구현 한다는 사실은 디버그할 때 표시 되는 호출 스택에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="bb511-117">자세한 내용은 [Runtime call stack](#CallStack) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb511-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb511-118">**.NET 네이티브 도구 체인을 사용하여 컴파일** 상자를 선택하거나 선택을 취소하여 디버그 및 릴리스 빌드가 .NET 네이티브 도구 체인을 사용하여 컴파일되는지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="bb511-119">단, Windows 스토어는 항상 .NET 네이티브 도구 체인을 사용하여 프로덕션 버전의 앱을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>
## <a name="runtime-exception-messages"></a><span data-ttu-id="bb511-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="bb511-120">Runtime exception messages</span></span>  
 <span data-ttu-id="bb511-121">애플리케이션 실행 파일 크기를 최소화하기 위해 .NET 네이티브에서는 예외 메시지의 전체 텍스트를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="bb511-122">결과적으로, 릴리스 빌드에서 런타임 예외가 throw될 경우 예외 메시지의 전체 텍스트가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="bb511-123">대신 자세한 정보에 대한 링크와 하위 문자열로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="bb511-124">예를 들어 예외 정보가 다음과 같이 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-124">For example, the exception information may appear as:</span></span>  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="bb511-125">전체 예외 메시지를 표시하려면 디버그 빌드를 대신 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="bb511-126">예를 들어 앞에서 릴리스 빌드에 나타난 예외 정보가 디버그 빌드에서는 다음과 같이 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>
## <a name="runtime-call-stack"></a><span data-ttu-id="bb511-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="bb511-127">Runtime call stack</span></span>  
 <span data-ttu-id="bb511-128">인라인 처리 및 기타 최적화로 인해 .NET 네이티브 도구 체인에 의해 컴파일된 앱에서 표시하는 호출 스택을 사용하면 런타임 예외 경로를 명확히 식별하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="bb511-129">전체 스택을 얻으려면 디버그 빌드를 대신 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb511-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb511-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb511-130">See also</span></span>

- [<span data-ttu-id="bb511-131">.NET 네이티브 Windows 유니버설 앱 디버깅</span><span class="sxs-lookup"><span data-stu-id="bb511-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="bb511-132">시작</span><span class="sxs-lookup"><span data-stu-id="bb511-132">Getting Started</span></span>](getting-started-with-net-native.md)
