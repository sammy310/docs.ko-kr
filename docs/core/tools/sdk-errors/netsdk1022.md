---
title: 'NETSDK1022: 중복 항목이 포함되었습니다.'
description: 기본 포함 내용에 따라 중복 항목 메시지를 해결하는 방법입니다.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717874"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: 중복 항목이 포함되었습니다.

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

Visual Studio 2017/MSBuild 버전 15.3부터 .NET SDK는 기본적으로 프로젝트 디렉터리의 항목을 자동으로 포함합니다.  여기에는 `Compile` 및 `Content` 대상이 포함됩니다.  따라서 프로젝트 파일을 많이 정리하여 복잡성을 줄여야 합니다.

올바른 속성을 false로 설정하여 이전 동작으로 되돌릴 수 있습니다.

`Compile` 항목에 대한 예제:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
