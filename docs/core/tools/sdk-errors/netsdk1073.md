---
title: 'NETSDK1073: FrameworkReference를 인식할 수 없음'
description: FrameworkReference를 찾을 수 없는 문제를 해결하는 방법입니다.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957098"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference를 인식할 수 없음

**이 문서의 적용 대상:** ✔️ .NET 2.1.100 SDK 이상 버전

일반적으로 이 오류는 SDK에서 찾을 수 없는 특정 FrameworkReference 버전이 있음을 의미합니다. *obj* 및 *bin* 폴더를 삭제하고 `dotnet restore`를 실행하여 최신 타기팅 팩을 다시 다운로드합니다.

또는 설치 관련 문제가 있을 수 있으므로 최신 버전의 .NET 및 Visual Studio를 사용하고 있는지 확인합니다.
