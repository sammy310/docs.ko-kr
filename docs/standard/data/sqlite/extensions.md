---
title: 확장
ms.date: 12/13/2019
description: SQLite 확장을 로드하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242961"
---
# <a name="extensions"></a>확장

SQLite는 런타임에 로딩 확장을 지원합니다. 확장에는 추가 SQL 함수, 데이터 정렬, 가상 테이블 등이 포함됩니다.

.NET Core에는 참조된 NuGet 패키지와 같은 추가 위치에 네이티브 라이브러리를 찾기 위한 추가 논리가 포함되어 있습니다. 안타깝게도 SQLite는 이 논리를 활용할 수 없습니다. 플랫폼 API를 호출하여 라이브러리를 로드합니다. 따라서 SQLite 확장을 로드하기 전에 PATH, LD_LIBRARY_PATH 또는 DYLD_LIBRARY_PATH 환경 변수를 수정해야 할 수 있습니다. 참조된 NuGet 패키지 내에서 현재 런타임에 대한 바이너리 찾기를 보여 주는 GitHub [샘플이](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) GitHub에 있습니다.

확장을 로드하려면 메서드를 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 호출합니다. Microsoft.Data.Sqlite는 연결이 닫혀 다시 열더라도 확장이 로드된 상태로 유지되도록 합니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>참고 항목

* [런타임 로드 가능 확장](https://www.sqlite.org/loadext.html)
