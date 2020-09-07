---
ms.openlocfilehash: 9ab1686f60bcdbfef5f18576be17aee8c931f9aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497045"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a><span data-ttu-id="95bf6-101">비 IFS Winsock BSP 또는 LSP가 있는 Windows 7에서 SqlConnection.Open이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-101">SqlConnection.Open fails on Windows 7 with non-IFS Winsock BSP or LSP present</span></span>

#### <a name="details"></a><span data-ttu-id="95bf6-102">설명</span><span class="sxs-lookup"><span data-stu-id="95bf6-102">Details</span></span>

<span data-ttu-id="95bf6-103">비 IFS Winsock BSP 또는 LSP가 있는 Windows 7 컴퓨터에서 실행 중인 .NET Framework 4.5에서 <xref:System.Data.SqlClient.SqlConnection.Open> 및 <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)>가 실패합니다. 비 IFS BSP 또는 LSP가 설치되어 있는지 여부를 확인하려면 <code>netsh WinSock Show Catalog</code> 명령을 사용하고 반환되는 모든 <code>Winsock Catalog Provider Entry</code> 항목을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-103"><xref:System.Data.SqlClient.SqlConnection.Open> and <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> fail in the .NET Framework 4.5 if running on a Windows 7 machine with a non-IFS Winsock BSP or LSP are present on the computer.To determine whether a non-IFS BSP or LSP is installed, use the <code>netsh WinSock Show Catalog</code> command, and examine every <code>Winsock Catalog Provider Entry</code> item that is returned.</span></span> <span data-ttu-id="95bf6-104">서비스 플래그 값이 <code>0x20000</code> 비트 집합을 가진 경우, 공급자는 IFS 핸들을 사용하고 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-104">If the Service Flags value has the <code>0x20000</code> bit set, the provider uses IFS handles and will work correctly.</span></span> <span data-ttu-id="95bf6-105"><code>0x20000</code> 비트가 지우기인 경우(집합 아님) 비 IFS BSP 또는 LSP입니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-105">If the <code>0x20000</code> bit is clear (not set), it is a non-IFS BSP or LSP.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="95bf6-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="95bf6-106">Suggestion</span></span>

<span data-ttu-id="95bf6-107">이 버그는 .NET Framework 4.5.2에서 수정되었으므로 .NET Framework를 업그레이드하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-107">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="95bf6-108">또는 설치된 모든 비 IFS Winsock LSP를 제거하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95bf6-108">Alternatively, it can be avoided by removing any installed non-IFS Winsock LSPs.</span></span>

| <span data-ttu-id="95bf6-109">이름</span><span class="sxs-lookup"><span data-stu-id="95bf6-109">Name</span></span>    | <span data-ttu-id="95bf6-110">값</span><span class="sxs-lookup"><span data-stu-id="95bf6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="95bf6-111">Scope</span><span class="sxs-lookup"><span data-stu-id="95bf6-111">Scope</span></span>   |<span data-ttu-id="95bf6-112">부</span><span class="sxs-lookup"><span data-stu-id="95bf6-112">Minor</span></span>|
|<span data-ttu-id="95bf6-113">버전</span><span class="sxs-lookup"><span data-stu-id="95bf6-113">Version</span></span>|<span data-ttu-id="95bf6-114">4.5</span><span class="sxs-lookup"><span data-stu-id="95bf6-114">4.5</span></span>|
|<span data-ttu-id="95bf6-115">형식</span><span class="sxs-lookup"><span data-stu-id="95bf6-115">Type</span></span>|<span data-ttu-id="95bf6-116">런타임</span><span class="sxs-lookup"><span data-stu-id="95bf6-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="95bf6-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="95bf6-117">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.Open`
- `M:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)`

-->
