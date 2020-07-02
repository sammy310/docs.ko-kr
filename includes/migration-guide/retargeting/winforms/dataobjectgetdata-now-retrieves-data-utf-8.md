---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616080"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="a8c58-101">DataObject.GetData가 이제 데이터를 UTF-8로 검색</span><span class="sxs-lookup"><span data-stu-id="a8c58-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="a8c58-102">설명</span><span class="sxs-lookup"><span data-stu-id="a8c58-102">Details</span></span>

<span data-ttu-id="a8c58-103">.NET Framework 4를 대상으로 하거나 .NET Framework 4.5.1 이하 버전에서 실행되는 앱의 경우, `DataObject.GetData`는 HTML 형식의 데이터를 ASCII 문자열로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a8c58-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="a8c58-104">그 결과 ASCII 문자가 아닌 문자(ASCII 코드가 0x7F보다 큰 문자)는 임의의 두 문자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8c58-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="a8c58-105">.NET Framework 4.5 이상을 대상으로 하거나 .NET Framework 4.5.2에서 실행되는 앱의 경우, `DataObject.GetData`는 HTML 형식의 데이터를 UTF-8로 검색하여 0x7F보다 큰 문자를 올바르게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c58-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a8c58-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a8c58-106">Suggestion</span></span>

<span data-ttu-id="a8c58-107">HTML 형식 문자열 인코딩 문제에 대한 해결 방법을 구현한 상태에서(예를 들어 클립보드에서 검색한 HTML 문자열을 <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> 메서드에 전달하여 명시적으로 인코딩함으로써) 앱의 대상을 버전 4에서 4.5로 다시 지정하려면 해당 해결 방법을 제거해야 합니다. 어떤 이유로 이전 동작이 필요한 경우 앱은 .NET Framework 4.0을 대상으로 하여 해당 동작을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c58-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="a8c58-108">이름</span><span class="sxs-lookup"><span data-stu-id="a8c58-108">Name</span></span>    | <span data-ttu-id="a8c58-109">값</span><span class="sxs-lookup"><span data-stu-id="a8c58-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a8c58-110">Scope</span><span class="sxs-lookup"><span data-stu-id="a8c58-110">Scope</span></span>   | <span data-ttu-id="a8c58-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a8c58-111">Edge</span></span>        |
| <span data-ttu-id="a8c58-112">버전</span><span class="sxs-lookup"><span data-stu-id="a8c58-112">Version</span></span> | <span data-ttu-id="a8c58-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a8c58-113">4.5.2</span></span>       |
| <span data-ttu-id="a8c58-114">형식</span><span class="sxs-lookup"><span data-stu-id="a8c58-114">Type</span></span>    | <span data-ttu-id="a8c58-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="a8c58-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a8c58-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a8c58-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
