---
title: 클라우드 네이티브 응용 프로그램 크기 조정
description: Azure Kubernetes Service를 사용 하 여 클라우드 네이티브 응용 프로그램을 확장 하 고 비용 효율적인 방식으로 사용자 수요를 충족 하도록 Azure Functions.
ms.date: 05/13/2020
ms.openlocfilehash: d425976eed248461a9c2e4fe03596f9f6dfd2eba
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613735"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="35ad1-103">클라우드 네이티브 응용 프로그램 크기 조정</span><span class="sxs-lookup"><span data-stu-id="35ad1-103">Scaling cloud-native applications</span></span>

<span data-ttu-id="35ad1-104">클라우드 호스팅 환경으로 전환 하는 경우 가장 자주 발생 하는 touted 이점 중 하나는 확장성입니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="35ad1-105">확장성 또는 응용 프로그램에서 각 사용자에 대 한 성능을 손상 시 키 지 않고 추가 사용자 부하를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="35ad1-106">가장 일반적으로 응용 프로그램을 작은 부분으로 분할 하 여 필요한 리소스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="35ad1-107">클라우드 공급 업체는 어디에서 나 전 세계 어디에서 든 지 대규모 확장성을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="35ad1-108">이 장에서는 클라우드 네이티브 응용 프로그램을 사용자 수요에 맞게 확장할 수 있는 기술을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="35ad1-109">이러한 기술은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="35ad1-109">These technologies include:</span></span>

- <span data-ttu-id="35ad1-110">컨테이너</span><span class="sxs-lookup"><span data-stu-id="35ad1-110">Containers</span></span>
- <span data-ttu-id="35ad1-111">오케스트레이터</span><span class="sxs-lookup"><span data-stu-id="35ad1-111">Orchestrators</span></span>
- <span data-ttu-id="35ad1-112">서버리스 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="35ad1-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="35ad1-113">[이전](centralized-configuration.md)
>[다음](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="35ad1-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
