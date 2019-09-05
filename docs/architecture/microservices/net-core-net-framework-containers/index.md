---
title: Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
description: 컨테이너화된 .NET 애플리케이션에 대한 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
ms.date: 09/11/2018
ms.openlocfilehash: 771d23cf4610e5778f0a144386754ce10d6ae144
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295218"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a>Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택

.NET에서 서버 쪽 컨테이너화된 Docker 애플리케이션을 빌드하는 데 지원되는 두 가지 프레임워크는 [.NET Framework 및 .NET Core](https://www.microsoft.com/net/download)입니다. 두 프레임워크는 여러 .NET 플랫폼 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다. 그러나 두 프레임워크 간에는 기본적인 차이가 있으며, 사용하는 프레임워크는 수행하려는 작업에 따라 달라집니다. 이 섹션에서는 각 프레임워크를 선택해야 하는 경우에 대한 지침을 제공합니다.

>[!div class="step-by-step"]
>[이전](../container-docker-introduction/docker-containers-images-registries.md)
>[다음](general-guidance.md)
