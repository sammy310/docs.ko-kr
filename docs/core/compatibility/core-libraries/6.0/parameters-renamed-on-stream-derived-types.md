---
title: '호환성이 손상되는 변경: 스트림 파생 형식의 매개 변수 이름이 변경됨'
description: 스트림 파생 형식의 메서드에서 일부 매개 변수 이름이 변경된 핵심 .NET 라이브러리의 .NET 6.0 호환성이 손상되는 변경을 알아봅니다.
ms.date: 03/04/2021
ms.openlocfilehash: c685fae6a7ed20ea47815d5f89a4e066c75e1178
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260007"
---
# <a name="some-parameters-in-stream-derived-types-are-renamed"></a><span data-ttu-id="ded21-103">스트림 파생 형식의 일부 매개 변수 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="ded21-103">Some parameters in Stream-derived types are renamed</span></span>

<span data-ttu-id="ded21-104">.NET 6에서는 <xref:System.IO.Stream?displayProperty=fullName>에서 파생된 형식에 대한 메서드의 일부 매개 변수 이름이 기본 클래스와 일치하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-104">In .NET 6, some parameters of methods on types derived from <xref:System.IO.Stream?displayProperty=fullName> have been renamed to match the base class.</span></span>

## <a name="change-description"></a><span data-ttu-id="ded21-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="ded21-105">Change description</span></span>

<span data-ttu-id="ded21-106">이전 .NET 버전에서는 <xref:System.IO.Stream>에서 파생된 여러 가지 형식이 메서드를 재정의하지만 기본 형식에서 사용되는 이름과는 다른 매개 변수 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-106">In previous .NET versions, several types derived from <xref:System.IO.Stream> override methods but use different parameter names than those used by the base type.</span></span> <span data-ttu-id="ded21-107">예를 들어, <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>의 바이트 배열 매개 변수 이름은 `array`로 지정되지만 기본 클래스 메서드의 해당 인수 이름은 `buffer`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-107">For example, the byte array parameter of <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> is named `array` while the corresponding argument in the base class method is named `buffer`.</span></span>

<span data-ttu-id="ded21-108">.NET 6에서 일치하지 않는 매개 변수 이름을 사용한 <xref:System.IO.Stream?displayProperty=fullName>에서 파생되는 모든 형식은 기본 형식과 동일한 매개 변수 이름을 사용하여 기본 형식을 준수하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-108">In .NET 6, all types that derive from <xref:System.IO.Stream?displayProperty=fullName> that had mismatched parameter names have been brought into conformance with the base type by using the same parameter names as the base type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ded21-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ded21-109">Version introduced</span></span>

<span data-ttu-id="ded21-110">6.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="ded21-110">6.0 Preview 1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ded21-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ded21-111">Reason for change</span></span>

<span data-ttu-id="ded21-112">변경에는 여러 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-112">There are several reasons for the change:</span></span>

- <span data-ttu-id="ded21-113">잘못된 인수가 전달되고 예외가 throw된 경우 해당 예외에는 구현에 따라 기본 매개 변수의 이름 또는 파생 매개 변수 이름이 포함되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-113">If an invalid argument was passed and an exception was thrown, that exception might have contained the base parameter's name or the derived parameter's name, depending on the implementation.</span></span> <span data-ttu-id="ded21-114">호출자가 기본 형식 또는 파생 형식으로 형식화된 참조를 사용했을 수 있으므로 예외의 인수 이름이 항상 올바를 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-114">Since the caller may have been using a reference typed as the base or as the derived type, it's impossible for the argument name in the exception to always be correct.</span></span>
- <span data-ttu-id="ded21-115">서로 다른 매개 변수 이름을 사용하면 모든 <xref:System.IO.Stream> 구현에서 동작의 유효성을 일관되게 검사하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-115">Having different parameter names makes it harder to consistently validate behavior across all <xref:System.IO.Stream> implementations.</span></span>
- <span data-ttu-id="ded21-116">.NET 6은 인수의 유효성을 검사하기 위해 <xref:System.IO.Stream>에 퍼블릭 메서드를 추가하고 해당 메서드에는 사용할 일관된 매개 변수 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-116">.NET 6 adds a public method on <xref:System.IO.Stream> for validating arguments, and that methods needs to have a consistent parameter name to use.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ded21-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ded21-117">Recommended action</span></span>

<span data-ttu-id="ded21-118">이 호환성이 손상되는 변경의 효과는 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-118">The effect of this breaking change is minimal:</span></span>

- <span data-ttu-id="ded21-119">기존 이진의 경우 변경의 영향은 영향을 받는 파생 형식에서 매개 변수 이름을 검사하는 데 리플렉션을 사용하는 코드로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-119">For existing binaries, its impact is limited to code that uses reflection to examine the names of parameters on the affected derived types.</span></span>
- <span data-ttu-id="ded21-120">소스 코드의 경우 변경의 영향은 파생 형식으로 형식화된 변수를 사용하여 파생 스트림 형식에서 메서드를 호출하는 데 명명된 매개 변수를 사용하는 코드로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-120">For source code, its impact is limited to code that uses named parameters to invoke methods on the derived stream type using a variable typed as that derived type.</span></span>

<span data-ttu-id="ded21-121">두 경우에 모두 기본 매개 변수 이름을 일관되게 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ded21-121">In both cases, the recommended action is to consistently use the base parameter name.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ded21-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ded21-122">Affected APIs</span></span>

- <xref:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`

-->
