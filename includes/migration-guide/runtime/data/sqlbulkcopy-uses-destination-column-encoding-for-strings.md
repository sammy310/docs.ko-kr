---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497232"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a><span data-ttu-id="04bea-101">SqlBulkCopy는 문자열에 대상 열 인코딩을 사용함</span><span class="sxs-lookup"><span data-stu-id="04bea-101">SqlBulkCopy uses destination column encoding for strings</span></span>

#### <a name="details"></a><span data-ttu-id="04bea-102">설명</span><span class="sxs-lookup"><span data-stu-id="04bea-102">Details</span></span>

<span data-ttu-id="04bea-103">열에 데이터를 삽입할 때 <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName>에서는 <code>VARCHAR</code> 및 <code>CHAR</code> 형식에 대한 기본 인코딩 대신 대상 열의 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04bea-103">When inserting data into a column, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> uses the encoding of the destination column rather than the default encoding for <code>VARCHAR</code> and <code>CHAR</code> types.</span></span> <span data-ttu-id="04bea-104">이러한 변경을 통해 대상 열에서 기본 인코딩을 사용하지 않는 경우 기본 인코딩을 사용하여 발생하는 데이터 손상의 가능성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="04bea-104">This change eliminates the possibility of data corruption caused by using the default encoding when the destination column does not use the default encoding.</span></span> <span data-ttu-id="04bea-105">드문 경우이지만 인코딩에서의 이 변경으로 인해 대상 열에 맞추기에는 너무 큰 데이터가 생성되는 경우, 기존 애플리케이션에서 SqlException 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04bea-105">In rare cases, an existing application may throw a SqlException exception if the change in encoding produces data that is too big to fit into the destination column.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="04bea-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="04bea-106">Suggestion</span></span>

<span data-ttu-id="04bea-107">인코딩 차이로 인해 <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName>이 더 이상 데이터를 손상시키지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04bea-107">Expect that <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> will no longer corrupt data due to encoding differences.</span></span> <span data-ttu-id="04bea-108">대상 열의 크기 제한 근처 문자열을 복사하는 경우 데이터를 미리 인코딩(데이터가 대상 열에 맞는지 확인하기 위해 복사)하거나 <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>을 catch해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04bea-108">If strings near the destination column's size limit are being copied, it may be necessary to either pre-encode data (to be copied to check that the data will fit in the destination column) or catch <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="04bea-109">이름</span><span class="sxs-lookup"><span data-stu-id="04bea-109">Name</span></span>    | <span data-ttu-id="04bea-110">값</span><span class="sxs-lookup"><span data-stu-id="04bea-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="04bea-111">Scope</span><span class="sxs-lookup"><span data-stu-id="04bea-111">Scope</span></span>   |<span data-ttu-id="04bea-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="04bea-112">Edge</span></span>|
|<span data-ttu-id="04bea-113">버전</span><span class="sxs-lookup"><span data-stu-id="04bea-113">Version</span></span>|<span data-ttu-id="04bea-114">4.5</span><span class="sxs-lookup"><span data-stu-id="04bea-114">4.5</span></span>|
|<span data-ttu-id="04bea-115">형식</span><span class="sxs-lookup"><span data-stu-id="04bea-115">Type</span></span>|<span data-ttu-id="04bea-116">런타임</span><span class="sxs-lookup"><span data-stu-id="04bea-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="04bea-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="04bea-117">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
