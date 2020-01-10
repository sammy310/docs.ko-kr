---
title: 메모리 내 데이터베이스
ms.date: 12/13/2019
description: 메모리 내 SQLite 데이터베이스를 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 16a9b6536fbfede203c24b757e96e28e7c49dc05
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777408"
---
# <a name="in-memory-databases"></a>메모리 내 데이터베이스

SQLite 메모리 내 데이터베이스는 디스크에 저장 되는 것이 아니라 메모리에 완전히 저장 된 데이터베이스입니다. 특수 한 데이터 원본 파일 이름 `:memory:`를 사용 하 여 메모리 내 데이터베이스를 만듭니다. 연결이 닫히면 데이터베이스가 삭제 됩니다. `:memory:`사용 하는 경우 각 연결에서 자체 데이터베이스를 만듭니다.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>공유 가능한 메모리 내 데이터베이스

`Mode=Memory`를 사용 하 고 연결 문자열에 `Cache=Shared`를 사용 하 여 여러 연결 간에 메모리 내 데이터베이스를 공유할 수 있습니다. `Data Source` 키워드는 메모리 내 데이터베이스에 이름을 지정 하는 데 사용 됩니다. 동일한 이름을 사용 하는 연결 문자열은 동일한 메모리 내 데이터베이스에 액세스 합니다. 하나 이상의 연결이 열린 상태로 유지 되는 한 데이터베이스는 지속 됩니다. 이를 보여 주는 [샘플](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) 은 GitHub에서 사용할 수 있습니다.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
