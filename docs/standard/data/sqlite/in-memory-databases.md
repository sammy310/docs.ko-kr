---
title: 메모리 내 데이터베이스
ms.date: 12/13/2019
description: 메모리 내 SQLite 데이터베이스를 사용하는 방법을 알아봅니다.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391210"
---
# <a name="in-memory-databases"></a>메모리 내 데이터베이스

SQLite 메모리 내 데이터베이스는 디스크가 아니라 전적으로 메모리에 저장되는 데이터베이스입니다. 특수한 데이터 원본 파일 이름 `:memory:`를 사용하여 메모리 내 데이터베이스를 만듭니다. 연결이 닫히면 데이터베이스가 삭제됩니다. `:memory:`를 사용하는 경우 각 연결에서 자체 데이터베이스를 만듭니다.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>공유 가능한 메모리 내 데이터베이스

연결 문자열에 `Mode=Memory` 및 `Cache=Shared`를 사용하여 여러 연결 간에 메모리 내 데이터베이스를 공유할 수 있습니다. `Data Source` 키워드는 메모리 내 데이터베이스에 이름을 지정하는 데 사용됩니다. 동일한 이름을 사용하는 연결 문자열은 동일한 메모리 내 데이터베이스에 액세스합니다. 하나 이상의 연결이 열린 상태로 유지되는 한 데이터베이스는 지속됩니다. 이를 보여 주는 [샘플](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs)은 GitHub에서 사용할 수 있습니다.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
