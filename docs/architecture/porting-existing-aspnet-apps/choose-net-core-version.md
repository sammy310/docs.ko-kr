---
title: 적절한 .NET Core 버전 선택
description: 어떤 버전의 .NET Core를 대상으로 결정 해야 하나요?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 401eead986ee8b67ed15be609d0b5d228773312d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401269"
---
# <a name="choose-the-right-net-core-version"></a>적절한 .NET Core 버전 선택

대상으로 하는 .NET Core 버전을 선택할 때 대부분의 조직에서 가장 큰 고려 사항은 지원 수명 주기입니다. LTS (장기 지원) 릴리스는 자주 제공 되지 않지만 현재 (LTS) 릴리스 보다 더 긴 지원 창이 있습니다. 현재 LTS 릴리스는 1 년 마다 배송 되도록 예약 됩니다. 고객은 대상으로 지정할 릴리스를 선택할 수 있으며, 동일한 컴퓨터에 .NET Core의 다른 릴리스를 함께 설치할 수 있습니다. LTS 릴리스는 수명 주기 내내 중요 하 고 호환 되는 픽스만 받습니다. 현재 릴리스는 이와 동일한 픽스를 수신 하며 호환 되는 혁신 및 기능을 사용 하 여 업데이트 됩니다. LTS 릴리스는 초기 릴리스 후 3 년 동안 지원 됩니다. 현재 릴리스는 이어지는 현재 또는 LTS 릴리스 후 3개월 동안 지원됩니다.

현재는 이전 버전의 .NET Core로 이동 하지 않았기 때문에 큰 .NET Framework 앱을 현재 .NET Core로 마이그레이션하기를 원하는 대부분의 고객이 안정적인 대상을 찾고 있을 수 있습니다. 이 경우 마이그레이션의 대상으로 가장 적합 한 .NET Core 버전은 현재 LTS 버전인 .NET Core 3.1입니다. .NET Core 3.1에 대 한 지원은 12 월 2022에 종료 됩니다. 계획 된 다음 LTS 릴리스는 .NET 6.0 년 11 월 2021에 제공 될 예정입니다.

.NET Core 3.1에서 .NET 5.0 (다음 버전)로 업데이트 하는 경우 .NET Framework에서 .NET Core로 이식 하는 것 보다 훨씬 더 많은 노력이 필요 합니다. 따라서 대부분의 고객에 대 한 권장 사항은 먼저 .NET Core 3.1로 업그레이드 하는 것입니다. 그런 다음 나중에 업그레이드 하기 전에 다음 업데이트가 최신 릴리스 (.NET 5.0)로 되어야 하는지 아니면 다음 LTS 릴리스 (.NET 6.0)를 기다려야 하는지 결정 합니다.

이 책에서는 .NET Framework 앱이 .NET Core 3.1로 업그레이드 된다고 가정 합니다.

## <a name="references"></a>참조

[.NET Core 및 .NET 5 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)

>[!div class="step-by-step"]
>[이전](migrate-aspnet-core-2-1.md)
>[다음](incremental-migration-strategies.md)
