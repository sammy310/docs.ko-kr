---
ms.openlocfilehash: 54ef49755dc0b9d1b821ae7999ab218626d455e1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556338"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="4b380-101">사용자 지정 EncoderFallbackBuffer 인스턴스는 재귀적으로 대체될 수 없음</span><span class="sxs-lookup"><span data-stu-id="4b380-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="4b380-102">사용자 지정 <xref:System.Text.EncoderFallbackBuffer> 인스턴스는 재귀적으로 대체될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="4b380-103"><xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>를 구현하면 대상 인코딩으로 변환할 수 있는 문자 시퀀스가 생겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="4b380-104">그렇지 않으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-104">Otherwise, an exception occurs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4b380-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="4b380-105">Change description</span></span>

<span data-ttu-id="4b380-106">런타임은 문자-바이트 트랜스코딩 작업 도중 형식이 잘못되었거나 변환할 수 없는 UTF-16 시퀀스를 검색하여 해당 문자를 <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> 메서드에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4b380-107">`Fallback` 메서드는 변환할 수 없는 원래 데이터를 대체할 문자를 결정하며, 이러한 문자는 루프에서 <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType>를 호출하여 드레이닝됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="4b380-108">그런 다음 런타임은 이러한 대체 문자를 대상 인코딩으로 트랜스코딩하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="4b380-109">이 작업이 성공하면 런타임은 원래 입력 문자열에서 중단된 위치에서 트랜스코딩을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="4b380-110">이전에는 <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>에 대한 사용자 지정 구현은 대상 인코딩으로 변환할 수 없는 문자 시퀀스를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-110">Previously, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="4b380-111">대체된 문자를 대상 인코딩으로 변환할 수 없는 경우 런타임은 대체 문자를 사용하여 <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> 메서드를 다시 한 번 호출하여 <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> 메서드가 새 대체 시퀀스를 반환할 것을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="4b380-112">이 프로세스는 런타임이 올바른 형식의 변환 가능한 대체를 확인하거나 최대 재귀 횟수에 도달할 때까지 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="4b380-113">.Net Core 3.0부터 <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>에 대한 사용자 지정 구현은 대상 인코딩으로 변환할 수 있는 문자 시퀀스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="4b380-114">대체된 문자를 대상 인코딩으로 트랜스 코딩할 수 없으면 <xref:System.ArgumentException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="4b380-115">런타임은 더 이상 <xref:System.Text.EncoderFallbackBuffer> 인스턴스에 대한 재귀 호출을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="4b380-116">이 동작은 다음 조건 중 세 가지를 모두 충족하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="4b380-117">런타임은 잘못된 형식의 UTF-16 시퀀스 또는 대상 인코딩으로 변환할 수 없는 UTF-16 시퀀스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="4b380-118">사용자 지정 <xref:System.Text.EncoderFallback>이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="4b380-119">사용자 지정 <xref:System.Text.EncoderFallback>은 잘못된 형식이거나 변환할 수 없는 새 UTF-16 시퀀스를 대체하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4b380-120">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4b380-120">Version introduced</span></span>

<span data-ttu-id="4b380-121">3.0</span><span class="sxs-lookup"><span data-stu-id="4b380-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4b380-122">권장 조치</span><span class="sxs-lookup"><span data-stu-id="4b380-122">Recommended action</span></span>

<span data-ttu-id="4b380-123">대부분의 개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="4b380-124">애플리케이션이 사용자 지정 <xref:System.Text.EncoderFallback> 및 <xref:System.Text.EncoderFallbackBuffer> 클래스를 사용하는 경우 런타임이 처음 <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> 메서드를 호출할 때 <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> 구현이 대상 인코딩으로 직접 변환할 수 있는 올바른 형식의 UTF-16 데이터로 대체 버퍼를 채우도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b380-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="4b380-125">범주</span><span class="sxs-lookup"><span data-stu-id="4b380-125">Category</span></span>

<span data-ttu-id="4b380-126">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="4b380-126">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4b380-127">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4b380-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
