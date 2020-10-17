---
title: 'NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음'
description: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957099"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059: 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있음

**이 문서의 적용 대상:** ✔️ .NET 2.1.100 SDK 이상 버전

.NET SDK가 NETSDK1059 경고를 실행하는 경우 프로젝트에 사용되지 않는 .NET CLI 도구가 포함되어 있는 것입니다. .NET 2.1을 기준으로 .NET SDK에 포함된 해당 도구는 프로젝트에서 명시적으로 참조할 필요가 없습니다. .NET 2.1로 마이그레이션하는 방법에 대한 자세한 내용은 [여기](https://aka.ms/dotnetclitools-in-box)에서 확인할 수 있습니다.
