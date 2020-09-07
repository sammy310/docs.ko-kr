---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497074"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="09fe7-101">PrintSystemJobInfo.JobStream에 기록된 데이터는 XPS 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="09fe7-102">설명</span><span class="sxs-lookup"><span data-stu-id="09fe7-102">Details</span></span>

<span data-ttu-id="09fe7-103"><xref:System.Printing.PrintSystemJobInfo.JobStream> 속성은 인쇄 작업 스트림을 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="09fe7-104">사용자는 이 스트림을 작성하여 기본 운영 체제 인쇄 구성 요소로 원시 데이터를 보낼 수 있습니다. Windows 8 이후 버전 Windows 운영 체제의 .NET Framework 4.5부터 이 스트림에 작성되는 데이터는 패키지 스트림과 같은 XPS 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="09fe7-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="09fe7-105">Suggestion</span></span>

<span data-ttu-id="09fe7-106">인쇄 내용을 출력하려면 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="09fe7-107"><xref:System.Windows.Xps.XpsDocumentWriter> 클래스를 사용하여 인쇄 내용을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="09fe7-108">이는 권장되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="09fe7-109"><xref:System.Printing.PrintSystemJobInfo.JobStream> 속성에서 반환된 스트림으로 전송된 데이터가 패키지 스트림과 같은 XPS 형식인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="09fe7-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="09fe7-110">이름</span><span class="sxs-lookup"><span data-stu-id="09fe7-110">Name</span></span>    | <span data-ttu-id="09fe7-111">값</span><span class="sxs-lookup"><span data-stu-id="09fe7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="09fe7-112">Scope</span><span class="sxs-lookup"><span data-stu-id="09fe7-112">Scope</span></span>   |<span data-ttu-id="09fe7-113">부</span><span class="sxs-lookup"><span data-stu-id="09fe7-113">Minor</span></span>|
|<span data-ttu-id="09fe7-114">버전</span><span class="sxs-lookup"><span data-stu-id="09fe7-114">Version</span></span>|<span data-ttu-id="09fe7-115">4.5</span><span class="sxs-lookup"><span data-stu-id="09fe7-115">4.5</span></span>|
|<span data-ttu-id="09fe7-116">형식</span><span class="sxs-lookup"><span data-stu-id="09fe7-116">Type</span></span>|<span data-ttu-id="09fe7-117">런타임</span><span class="sxs-lookup"><span data-stu-id="09fe7-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="09fe7-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="09fe7-118">Affected APIs</span></span>

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
