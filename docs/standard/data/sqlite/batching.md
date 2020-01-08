---
title: 일괄 처리
ms.date: 12/13/2019
description: 단일 명령으로 SQL 문의 일괄 처리를 실행 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450311"
---
# <a name="batching"></a><span data-ttu-id="63521-103">일괄 처리</span><span class="sxs-lookup"><span data-stu-id="63521-103">Batching</span></span>

<span data-ttu-id="63521-104">SQLite는 기본적으로 SQL 문 일괄 처리를 단일 명령으로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63521-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="63521-105">그러나 네트워크와 관련 된 네트워크는 없기 때문에 실제 성능에는 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63521-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="63521-106">그러나 ADO.NET은 다른 공급자 처럼 동작 하도록 하기 위한 편의를 위해 문 일괄 처리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="63521-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="63521-107"><xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>를 호출할 때 문은 결과를 반환 하는 첫 번째 문으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63521-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="63521-108"><xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType>를 호출 하면 그 다음에 결과를 반환할 때까지 또는 일괄 처리의 끝에 도달할 때까지 문을 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="63521-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="63521-109"><xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> 또는 <xref:System.Data.Common.DbDataReader.Close%2A>를 호출 하면 `NextResult()`에서 사용 되지 않은 나머지 모든 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63521-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="63521-110">데이터 판독기를 삭제 하지 않으면 종료 자가 나머지 문을 실행 하려고 시도 하지만 발견 한 오류는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63521-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="63521-111">따라서 일괄 처리를 사용 하는 경우 `DbDataReader` 개체를 삭제 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="63521-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="63521-112">참조</span><span class="sxs-lookup"><span data-stu-id="63521-112">See also</span></span>

* [<span data-ttu-id="63521-113">대량 삽입</span><span class="sxs-lookup"><span data-stu-id="63521-113">Bulk Insert</span></span>](bulk-insert.md)
