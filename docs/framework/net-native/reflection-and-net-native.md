---
description: '자세한 정보: 리플렉션 및 .NET 네이티브'
title: 리플렉션 및 .NET 네이티브
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
ms.openlocfilehash: 150afe5964cbf3a8983540d5948b246a8f330793
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738444"
---
# <a name="reflection-and-net-native"></a><span data-ttu-id="12c2e-103">리플렉션 및 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="12c2e-103">Reflection and .NET Native</span></span>

<span data-ttu-id="12c2e-104">.NET Framework의 관리 개발에서는 리플렉션 API를 통한 메타 프로그래밍이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-104">In the .NET Framework, managed development supports metaprogramming through the reflection API.</span></span> <span data-ttu-id="12c2e-105">리플렉션을 통해 앱의 개체를 검사하고, 검사를 통해 검색된 개체에 대해 메서드를 호출하고, 런타임에 새 형식을 생성하고, 기타 여러 동적 코드 시나리오를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-105">Reflection allows you to inspect objects in an app, call methods on objects discovered through inspection, generate new types at run time, and supports many other dynamic code scenarios.</span></span> <span data-ttu-id="12c2e-106">또한 serialization과 deserialization도 지원되므로 개체의 필드 값을 유지했다가 나중에 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-106">It also supports serialization and deserialization, which allows an object's field values to be persisted and later restored.</span></span> <span data-ttu-id="12c2e-107">이러한 모든 시나리오에서는 .NET Framework JIT(Just-In-Time) 컴파일러가 사용 가능한 메타데이터를 기반으로 네이티브 코드를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-107">These scenarios all require the .NET Framework just-in-time (JIT) compiler to generate native code based on available metadata.</span></span>  
  
 <span data-ttu-id="12c2e-108">.NET 네이티브 런타임은 JIT 컴파일러를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-108">The .NET Native runtime doesn't include a JIT compiler.</span></span> <span data-ttu-id="12c2e-109">따라서 필요한 모든 네이티브 코드를 미리 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-109">As a result, all necessary native code must be generated in advance.</span></span> <span data-ttu-id="12c2e-110">추론 집합을 사용하여 생성해야 하는 코드를 결정할 수 있지만 이러한 추론이 가능한 모든 프로그래밍 시나리오에 적용되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-110">A set of heuristics is used to determine what code should be generated, but these heuristics cannot cover all possible metaprogramming scenarios.</span></span>  <span data-ttu-id="12c2e-111">그러므로 [런타임 지시문](runtime-directives-rd-xml-configuration-file-reference.md)을 사용하여 이러한 메타 프로그래밍 시나리오에 대한 힌트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-111">Therefore, you must provide hints for these metaprogramming scenarios by using [runtime directives](runtime-directives-rd-xml-configuration-file-reference.md).</span></span> <span data-ttu-id="12c2e-112">필요한 메타데이터 또는 구현 코드를 런타임에 사용할 수 없는 경우 앱에서는 [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) 또는 [MissingInteropDataException](missinginteropdataexception-class-net-native.md) 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-112">If the necessary metadata or implementation code is not available at runtime, your app throws a [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md), or [MissingInteropDataException](missinginteropdataexception-class-net-native.md) exception.</span></span> <span data-ttu-id="12c2e-113">이 예외를 제거하는 런타임 지시문 파일에 대한 적절한 항목을 생성하는 두 가지 문제 해결사를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-113">Two troubleshooters are available that will generate the appropriate entry for your runtime directives file that eliminates the exception:</span></span>  
  
- <span data-ttu-id="12c2e-114">형식의 경우 [MissingMetadataException 문제 해결사](https://dotnet.github.io/native/troubleshooter/type.html) 입니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-114">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/type.html) for types.</span></span>  
  
- <span data-ttu-id="12c2e-115">메서드의 경우 [MissingMetadataException 문제 해결사](https://dotnet.github.io/native/troubleshooter/method.html) 입니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-115">The [MissingMetadataException troubleshooter](https://dotnet.github.io/native/troubleshooter/method.html) for methods.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12c2e-116">런타임 지시문 파일이 필요한 이유에 대한 배경 정보를 제공하는 .NET 네이티브 컴파일 프로세스의 개요는 [.NET 네이티브 및 컴파일](net-native-and-compilation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12c2e-116">For an overview of the .NET Native compilation process that provides background on why a runtime directives file is needed, see [.NET Native and Compilation](net-native-and-compilation.md).</span></span>  
  
 <span data-ttu-id="12c2e-117">또한 .NET 네이티브를 사용 하면 .NET Framework 클래스 라이브러리의 전용 멤버를 반영할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-117">In addition, .NET Native doesn't allow you to reflect over private members of the .NET Framework class library.</span></span> <span data-ttu-id="12c2e-118">예를 들어 .NET Framework 클래스 라이브러리 형식의 필드를 검색하기 위해 <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> 속성을 호출하면 공용 필드 또는 보호된 필드만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-118">For example, a call to the <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> property to retrieve the fields of a .NET Framework class library type returns only public or protected fields.</span></span>  
  
 <span data-ttu-id="12c2e-119">다음 항목에서는 앱에서 리플렉션과 serialization을 지원하는 데 필요한 개념 및 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12c2e-119">The following topics provide the conceptual and reference documentation that you need to support reflection and serialization in your apps:</span></span>  
  
- [<span data-ttu-id="12c2e-120">리플렉션을 사용하는 API</span><span class="sxs-lookup"><span data-stu-id="12c2e-120">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)  
  
- [<span data-ttu-id="12c2e-121">리플렉션 API 참조</span><span class="sxs-lookup"><span data-stu-id="12c2e-121">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)  
  
- [<span data-ttu-id="12c2e-122">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="12c2e-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="12c2e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12c2e-123">See also</span></span>

- [<span data-ttu-id="12c2e-124">.NET Native로 앱 컴파일</span><span class="sxs-lookup"><span data-stu-id="12c2e-124">Compiling Apps with .NET Native</span></span>](index.md)
- [<span data-ttu-id="12c2e-125">.NET 네이티브 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="12c2e-125">.NET Native and Compilation</span></span>](net-native-and-compilation.md)
