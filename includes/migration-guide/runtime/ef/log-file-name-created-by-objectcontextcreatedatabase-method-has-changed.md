---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620316"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="84e76-101">ObjectContext.CreateDatabase 메서드로 만든 로그 파일 이름이 SQL Server 사양에 맞게 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e76-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="84e76-102">설명</span><span class="sxs-lookup"><span data-stu-id="84e76-102">Details</span></span>

<span data-ttu-id="84e76-103"><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> 메서드를 직접 호출하거나 SqlClient 공급자로 Code First를 사용하고 연결 문자열의 AttachDBFilename 값을 사용하여 호출하면 filename.ldf 대신 filename_log.ldf라는 로그 파일이 생성됩니다(filename이 AttachDBFilename 값으로 지정한 파일 이름인 경우).</span><span class="sxs-lookup"><span data-stu-id="84e76-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="84e76-104">이 변경을 통해 SQL Server 사양에 따라 명명된 로그 파일을 제공하여 디버깅을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="84e76-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="84e76-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="84e76-105">Suggestion</span></span>

<span data-ttu-id="84e76-106">로그 파일 이름이 응용 프로그램에서 중요한 경우 응용 프로그램은 표준 _log.ldf 파일 이름 형식을 사용하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84e76-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="84e76-107">이름</span><span class="sxs-lookup"><span data-stu-id="84e76-107">Name</span></span>    | <span data-ttu-id="84e76-108">값</span><span class="sxs-lookup"><span data-stu-id="84e76-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="84e76-109">Scope</span><span class="sxs-lookup"><span data-stu-id="84e76-109">Scope</span></span>   |<span data-ttu-id="84e76-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="84e76-110">Edge</span></span>|
|<span data-ttu-id="84e76-111">버전</span><span class="sxs-lookup"><span data-stu-id="84e76-111">Version</span></span>|<span data-ttu-id="84e76-112">4.5</span><span class="sxs-lookup"><span data-stu-id="84e76-112">4.5</span></span>|
|<span data-ttu-id="84e76-113">형식</span><span class="sxs-lookup"><span data-stu-id="84e76-113">Type</span></span>|<span data-ttu-id="84e76-114">런타임</span><span class="sxs-lookup"><span data-stu-id="84e76-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="84e76-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="84e76-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
