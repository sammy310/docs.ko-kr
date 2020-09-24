---
ms.openlocfilehash: 6ffd4147a99a59d0a2e50d3f88279608e286aed1
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90680017"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="3a677-101">CryptoStream.Dispose는 쓰는 경우에만 최종 블록을 변환함</span><span class="sxs-lookup"><span data-stu-id="3a677-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="3a677-102">`CryptoStream` 연산을 완료하기 위해 사용되는 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> 메서드는 읽을 때 더 이상 최종 블록을 변환하려고 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3a677-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3a677-103">Change description</span></span>

<span data-ttu-id="3a677-104">이전 .NET 버전에서는 사용자가 <xref:System.Security.Cryptography.CryptoStreamMode.Read> 모드에서 <xref:System.Security.Cryptography.CryptoStream>을 사용할 때 불완전한 읽기를 수행하는 경우 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> 메서드가 예외를 throw할 수 있습니다(예: 패딩이 포함된 AES를 사용할 경우).</span><span class="sxs-lookup"><span data-stu-id="3a677-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="3a677-105">최종 블록을 변환하려고 시도했지만 데이터가 불완전하기 때문에 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="3a677-106">.NET Core 3.0 이상 버전에서 <xref:System.Security.Cryptography.CryptoStream.Dispose%2A>는 읽을 때 더 이상 최종 블록을 변환(불완전한 읽기가 가능함)하려고 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3a677-107">변경 이유</span><span class="sxs-lookup"><span data-stu-id="3a677-107">Reason for change</span></span>

<span data-ttu-id="3a677-108">이렇게 변경하면 네트워크 작업이 취소되는 경우 예외를 catch하지 않고도 암호화 스트림에서 불완전한 읽기가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-108">This change enables incomplete reads from the crypto stream when a network operation is canceled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3a677-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3a677-109">Version introduced</span></span>

<span data-ttu-id="3a677-110">3.0</span><span class="sxs-lookup"><span data-stu-id="3a677-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3a677-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3a677-111">Recommended action</span></span>

<span data-ttu-id="3a677-112">대부분의 앱은 이 변경의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="3a677-113">불완전한 읽기 발생 시 애플리케이션이 이전에 예외를 catch했다면 해당 `catch` 블록을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="3a677-114">해시 시나리오에서 앱이 최종 블록의 변환을 사용한 경우 삭제하기 전에 전체 스트림을 읽었는지 확인해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a677-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="3a677-115">범주</span><span class="sxs-lookup"><span data-stu-id="3a677-115">Category</span></span>

<span data-ttu-id="3a677-116">암호화</span><span class="sxs-lookup"><span data-stu-id="3a677-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a677-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3a677-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
