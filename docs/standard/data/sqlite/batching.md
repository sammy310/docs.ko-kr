---
title: 일괄 처리
ms.date: 12/13/2019
description: 단일 명령으로 SQL 문의 일괄 처리를 실행하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450311"
---
# <a name="batching"></a><span data-ttu-id="99367-103">일괄 처리</span><span class="sxs-lookup"><span data-stu-id="99367-103">Batching</span></span>

<span data-ttu-id="99367-104">SQLite는 기본적으로 SQL 문을 단일 명령으로 일괄 처리하는 것을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99367-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="99367-105">그러나 관련된 네트워크가 없기 때문에 실제 성능에는 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99367-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="99367-106">다만 Microsoft.Data.Sqlite는 편의상 다른 ADO.NET 공급자처럼 동작하도록 하기 위해 명령문 일괄 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="99367-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="99367-107"><xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>을 호출하면 명령문은 결과를 반환하는 첫 번째 명령문까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="99367-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="99367-108"><xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType>을 호출하면 결과를 반환하는 다음 명령문 또는 일괄 처리의 끝에 도달할 때까지 명령문을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99367-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="99367-109"><xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 또는 <xref:System.Data.Common.DbDataReader.Close%2A>를 호출하면 `NextResult()`에서 사용되지 않은 나머지 명령문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="99367-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="99367-110">데이터 판독기를 삭제하지 않으면 종료자가 나머지 명령문을 실행하려고 하지만 발생한 오류는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99367-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="99367-111">이로 인해 일괄 처리를 사용할 때는 `DbDataReader` 개체를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99367-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="99367-112">참조</span><span class="sxs-lookup"><span data-stu-id="99367-112">See also</span></span>

* [<span data-ttu-id="99367-113">대량 삽입</span><span class="sxs-lookup"><span data-stu-id="99367-113">Bulk Insert</span></span>](bulk-insert.md)
