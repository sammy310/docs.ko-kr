---
title: 'NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음'
description: 자산 파일에 대상이 없는 문제를 해결하는 방법입니다.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 6c22fd8c79c2ac6e024b46b4f67e08011d42efc6
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957103"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 및 NETSDK1047: 자산 파일에 대상이 없음

**이 문서의 적용 대상:** ✔️ .NET 2.1.100 SDK 이상 버전

.NET SDK가 NETSDK1005 또는 NETSDK1047 오류를 실행하는 경우 프로젝트의 자산 파일에 대상 프레임워크 중 하나의 정보가 누락된 것입니다. 일반적으로 복원을 실행하고 누락된 대상 값을 프로젝트의 `TargetFrameworks` 속성에 포함하면 이 문제를 해결할 수 있습니다.

> [!NOTE]
> 이 오류가 발생한 Visual Studio 16.8 미리 보기 버전과 함께 사용할 경우 .NET 5 미리 보기 8 초기 빌드에 알려진 문제가 있었습니다. 특히, 누락된 대상이 `net5.0-windows7.0` 또는 `net5.0`인 경우 최신 버전의 Visual Studio 및 .NET 5 SDK로 업데이트했는지 확인합니다.
