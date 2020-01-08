---
title: 온라인 백업
ms.date: 12/13/2019
description: SQLite의 온라인 백업 기능을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450347"
---
# <a name="online-backup"></a><span data-ttu-id="c6c4e-103">온라인 백업</span><span class="sxs-lookup"><span data-stu-id="c6c4e-103">Online backup</span></span>

<span data-ttu-id="c6c4e-104">SQLite는 앱이 실행 되는 동안 데이터베이스 파일을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="c6c4e-105">이 기능은 `SqliteConnection`의 <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> 방법으로 서 Microsoft. Sqlite에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="c6c4e-106">현재는 `BackupDatabase` 데이터베이스를 가능한 한 빨리 백업 하 고 다른 연결에서 데이터베이스에 쓰는 것을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="c6c4e-107">문제 [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) 은 백그라운드에서 데이터베이스를 백업 하는 대체 API를 제공 하 고, 다른 연결에서 백업을 중단 하 고 데이터베이스에 쓸 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="c6c4e-108">관심이 있는 경우 문제에 대 한 피드백을 제공 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6c4e-108">If you're interested, provide feedback on the issue.</span></span>
