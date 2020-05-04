---
title: 온라인 백업
ms.date: 12/13/2019
description: SQLite의 온라인 백업 기능을 사용하는 방법을 알아봅니다.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901277"
---
# <a name="online-backup"></a><span data-ttu-id="868b1-103">온라인 백업</span><span class="sxs-lookup"><span data-stu-id="868b1-103">Online backup</span></span>

<span data-ttu-id="868b1-104">SQLite는 앱이 실행되는 동안 데이터베이스 파일을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="868b1-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="868b1-105">이 기능은 Microsoft.Data.Sqlite에서 `SqliteConnection`에 대한 <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> 메서드로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="868b1-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="868b1-106">현재는 `BackupDatabase`가 데이터베이스를 가능한 한 빨리 백업하고 다른 연결에서 데이터베이스에 쓰는 것을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="868b1-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="868b1-107">문제 [#13834](https://github.com/dotnet/efcore/issues/13834)는 백그라운드에서 데이터베이스를 백업하고 다른 연결에서 백업을 중단하고 데이터베이스에 쓸 수 있는 대체 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="868b1-107">Issue [#13834](https://github.com/dotnet/efcore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="868b1-108">관심이 있는 경우 이 문제에 대한 피드백을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="868b1-108">If you're interested, provide feedback on the issue.</span></span>
