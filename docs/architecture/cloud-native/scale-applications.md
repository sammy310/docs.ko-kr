---
title: 클라우드 네이티브 응용 프로그램 크기 조정
description: Azure Kubernetes Service를 사용 하 여 클라우드 네이티브 응용 프로그램을 확장 하 고 비용 효율적인 방식으로 사용자 수요를 충족 하도록 Azure Functions.
ms.date: 09/23/2019
ms.openlocfilehash: 5f4aac5804c5498c331787083c943a6ea1b69748
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841032"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="db2bf-103">클라우드 네이티브 응용 프로그램 크기 조정</span><span class="sxs-lookup"><span data-stu-id="db2bf-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="db2bf-104">클라우드 호스팅 환경으로 전환 하는 경우 가장 자주 발생 하는 touted 이점 중 하나는 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="db2bf-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="db2bf-105">확장성 또는 응용 프로그램에서 각 사용자에 대 한 성능을 지나치게 저하 시 키 지 않고 추가 사용자 부하를 허용 하는 기능은 응용 프로그램을 각각 필요한 리소스를 제공 하는 작은 부분으로 분할 하 여 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db2bf-105">Scalability, or the ability for an application to accept additional user load without unduly degrading performance for each user, is most often achieved by breaking up applications into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="db2bf-106">이 장에서는 클라우드 네이티브 응용 프로그램을 사용자 수요에 맞게 확장할 수 있는 기술을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="db2bf-106">In this chapter, we introduce the technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="db2bf-107">이러한 기술은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db2bf-107">These technologies include:</span></span>

- <span data-ttu-id="db2bf-108">컨테이너</span><span class="sxs-lookup"><span data-stu-id="db2bf-108">Containers</span></span>
- <span data-ttu-id="db2bf-109">Orchestrator</span><span class="sxs-lookup"><span data-stu-id="db2bf-109">Orchestrators</span></span>
- <span data-ttu-id="db2bf-110">서버를 사용 하지 않는 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="db2bf-110">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="db2bf-111">[이전](centralized-configuration.md)
>[다음](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="db2bf-111">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
