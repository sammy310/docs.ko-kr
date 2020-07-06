---
ms.openlocfilehash: f87b70708398226516ab5eac32c24a9fc2c1106b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615738"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a><span data-ttu-id="2e784-101">잘못된 서로게이트 쌍에서 XmlWriter가 throw함</span><span class="sxs-lookup"><span data-stu-id="2e784-101">XmlWriter throws on invalid surrogate pairs</span></span>

#### <a name="details"></a><span data-ttu-id="2e784-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2e784-102">Details</span></span>

<span data-ttu-id="2e784-103">.NET Framework 4.5.2 또는 이전 버전을 대상으로 하는 앱의 경우 예외 대체(fallback) 처리를 사용하여 잘못된 서로게이트 쌍을 작성해도 항상 예외가 발생하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e784-103">For apps that target the .NET Framework 4.5.2 or previous versions, writing an invalid surrogate pair using exception fallback handling does not always throw an exception.</span></span> <span data-ttu-id="2e784-104">.NET Framework 4.6을 대상으로 하는 앱의 경우 잘못된 서로게이트 쌍을 쓰려고 하면 <xref:System.ArgumentException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="2e784-104">For apps that target the .NET Framework 4.6, attempting to write an invalid surrogate pair throws an <xref:System.ArgumentException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2e784-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2e784-105">Suggestion</span></span>

<span data-ttu-id="2e784-106">필요한 경우 .NET Framework 4.5.2 이전 버전을 대상으로 하여 이 중단을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e784-106">If necessary, this break can be avoided by targeting the .NET Framework 4.5.2 or earlier.</span></span> <span data-ttu-id="2e784-107">또는 잘못된 서로게이트 쌍을 쓰기 전에 유효한 xml로 사전 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e784-107">Alternatively, invalid surrogate pairs can be pre-processed into valid xml prior to writing them.</span></span>

| <span data-ttu-id="2e784-108">이름</span><span class="sxs-lookup"><span data-stu-id="2e784-108">Name</span></span>    | <span data-ttu-id="2e784-109">값</span><span class="sxs-lookup"><span data-stu-id="2e784-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2e784-110">Scope</span><span class="sxs-lookup"><span data-stu-id="2e784-110">Scope</span></span>   | <span data-ttu-id="2e784-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2e784-111">Edge</span></span>        |
| <span data-ttu-id="2e784-112">버전</span><span class="sxs-lookup"><span data-stu-id="2e784-112">Version</span></span> | <span data-ttu-id="2e784-113">4.6</span><span class="sxs-lookup"><span data-stu-id="2e784-113">4.6</span></span>         |
| <span data-ttu-id="2e784-114">형식</span><span class="sxs-lookup"><span data-stu-id="2e784-114">Type</span></span>    | <span data-ttu-id="2e784-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="2e784-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2e784-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2e784-116">Affected APIs</span></span>

- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType>
