---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009062"
---
### <a name="xml-parsing-changes"></a><span data-ttu-id="1253d-101">XML 구문 분석 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1253d-101">XML parsing changes</span></span>

| <span data-ttu-id="1253d-102">Name</span><span class="sxs-lookup"><span data-stu-id="1253d-102">Name</span></span>    | <span data-ttu-id="1253d-103">값</span><span class="sxs-lookup"><span data-stu-id="1253d-103">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="1253d-104">Scope</span><span class="sxs-lookup"><span data-stu-id="1253d-104">Scope</span></span>   | <span data-ttu-id="1253d-105">부</span><span class="sxs-lookup"><span data-stu-id="1253d-105">Minor</span></span>   |
| <span data-ttu-id="1253d-106">버전</span><span class="sxs-lookup"><span data-stu-id="1253d-106">Version</span></span> | <span data-ttu-id="1253d-107">4.5.2</span><span class="sxs-lookup"><span data-stu-id="1253d-107">4.5.2</span></span>   |
| <span data-ttu-id="1253d-108">형식</span><span class="sxs-lookup"><span data-stu-id="1253d-108">Type</span></span>    | <span data-ttu-id="1253d-109">런타임</span><span class="sxs-lookup"><span data-stu-id="1253d-109">Runtime</span></span> |

#### <a name="details"></a><span data-ttu-id="1253d-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1253d-110">Details</span></span>

<span data-ttu-id="1253d-111">보안상의 이유로 XML 구문 분석 API에 다음 변경 내용이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-111">For security reasons, the following changes were introduced into XML parsing APIS:</span></span>

- <span data-ttu-id="1253d-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType>는 <xref:System.Xml.XmlReaderSettings>가 초기화될 때 1,000만으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> is set to 10 million when <xref:System.Xml.XmlReaderSettings> is initialized.</span></span>
- <span data-ttu-id="1253d-113">기본적으로 <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType>은 `null`으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> is set to `null` by default.</span></span>

> [!NOTE]
> <span data-ttu-id="1253d-114"><xref:System.Xml.XmlReaderSettings>는 모든 XML 파서에서 사용되므로 이 변경 내용은 <xref:System.Xml.XmlReader> 사례에 도움이 되며 다른 시나리오에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-114"><xref:System.Xml.XmlReaderSettings> is used by all XML parsers, so while this change helps the <xref:System.Xml.XmlReader> case, it also affects other scenarios.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1253d-115">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="1253d-115">Suggestion</span></span>

<span data-ttu-id="1253d-116">이전 동작으로 되돌리려면 레지스트리에서 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-116">To revert to the previous behavior, you can set a value in the registry.</span></span> <span data-ttu-id="1253d-117">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` 레지스트리 키에 `EnableLegacyXmlSettings`라는 DWORD 값을 추가하고 해당 값을 `1`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-117">Add a DWORD value named `EnableLegacyXmlSettings` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` registry key, and set its value to `1`.</span></span> <span data-ttu-id="1253d-118">대신 HKEY_CURRENT_USER 하이브에서 레지스트리 값을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-118">You can also add the registry value in the HKEY_CURRENT_USER hive instead.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1253d-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1253d-119">Affected APIs</span></span>

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

<span data-ttu-id="1253d-120">또한 <xref:System.Xml.XmlResolver>에 직접 또는 간접적으로 종속된 모든 XML API가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1253d-120">In addition, any XML API that depends on <xref:System.Xml.XmlResolver>, either directly or indirectly, is affected.</span></span>

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
