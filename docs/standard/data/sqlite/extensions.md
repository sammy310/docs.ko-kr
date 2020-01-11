---
title: 확장명
ms.date: 12/13/2019
description: SQLite 확장을 로드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a85b1227be4274dd20156d2475d6d2d68e250f99
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901292"
---
# <a name="extensions"></a>확장명

SQLite는 런타임에 확장 로드를 지원 합니다. 확장에는 추가 SQL 함수, 데이터 정렬, 가상 테이블 등과 같은 항목이 포함 됩니다.

.NET Core에는 참조 된 NuGet 패키지와 같은 추가 위치에서 네이티브 라이브러리를 찾기 위한 추가 논리가 포함 됩니다. 아쉽게도 SQLite는이 논리를 활용할 수 없습니다. 플랫폼 API를 직접 호출 하 여 라이브러리를 로드 합니다. 따라서 SQLite 확장을 로드 하기 전에 PATH, LD_LIBRARY_PATH 또는 DYLD_LIBRARY_PATH 환경 변수를 수정 해야 할 수 있습니다. 참조 된 NuGet 패키지 내에서 현재 런타임에 대 한 이진 파일 찾기를 보여 주는 [샘플은](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) GitHub에 있습니다.

확장을 로드 하려면 <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> 메서드를 호출 합니다. 연결을 닫았다가 다시 열면 확장이 로드 된 상태로 유지 됩니다.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>참조

* [런타임 로드 가능한 확장](https://www.sqlite.org/loadext.html)
