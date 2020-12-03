---
title: 'NETSDK1073: FrameworkReference를 인식할 수 없음'
description: FrameworkReference를 찾을 수 없는 문제를 해결하는 방법입니다.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713030"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: FrameworkReference를 인식할 수 없음

**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전

일반적으로 이 오류는 SDK에서 찾을 수 없는 특정 FrameworkReference 버전이 있음을 의미합니다. *obj* 및 *bin* 폴더를 삭제하고 `dotnet restore`를 실행하여 최신 타기팅 팩을 다시 다운로드합니다.

또는 설치 관련 문제가 있을 수 있으므로 최신 버전의 .NET 및 Visual Studio를 사용하고 있는지 확인합니다.
