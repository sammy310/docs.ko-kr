---
title: 기존.NET 앱을 클라우드 액세스에 최적화된 응용 프로그램으로 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: edbffe45a2a1652ff477f9785b3afb5b0e493bc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811680"
---
# <a name="modernize-existing-net-apps-to-cloud-optimized-applications"></a><span data-ttu-id="6b6a5-103">기존.NET 앱을 클라우드 액세스에 최적화된 응용 프로그램으로 최신화</span><span class="sxs-lookup"><span data-stu-id="6b6a5-103">Modernize existing .NET apps to Cloud-Optimized applications</span></span>

> <span data-ttu-id="6b6a5-104">목표: 기존 .NET Framework 응용 프로그램을 더 빠르게 제공하고 응용 프로그램을 인도하는 비용을 절감할 수 있도록 배포의 민첩성을 대폭 개선함으로써 클라우드 액세스에 최적화된 응용 프로그램으로 최신화합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-104">Vision: Modernize your existing .NET Framework applications to Cloud-Optimized applications to drastically improve your deployment agility, so you can ship faster and lower application’s delivery costs.</span></span>

<span data-ttu-id="6b6a5-105">컨테이너와 같은 새로운 기술과 클라우드의 이점을 활용하려면 기존 .NET 응용 프로그램을 부분적으로나마 최신화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-105">To take advantage of the benefits of the cloud and new technologies like containers, you should at least partially modernize your existing .NET applications.</span></span> <span data-ttu-id="6b6a5-106">궁극적으로, 엔터프라이즈 응용 프로그램을 최신화하면 총 소유 비용이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-106">Ultimately, modernizing your enterprise applications will lower your total cost of ownership.</span></span>

<span data-ttu-id="6b6a5-107">부분적인 앱의 최신화가 반드시 전체 마이그레이션과 재구성을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-107">Partially modernizing an app doesn’t necessarily mean a full migration and rearchitecture.</span></span> <span data-ttu-id="6b6a5-108">처음에는 중요하지만 쉽게 최신화가 가능한 기존 응용 프로그램을 최신화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-108">You can initially modernize your existing applications with important but easy to do modernization.</span></span> <span data-ttu-id="6b6a5-109">모든 Windows와 IIS 종속성을 사용하여 기존 .NET Framework 버전으로 작성된 현재 코드베이스를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-109">You can maintain your current code base, written in existing .NET Framework versions, with any Windows and IIS dependencies.</span></span> <span data-ttu-id="6b6a5-110">그림 4-1에서는 클라우드에 최적화된 앱이 Azure 응용 프로그램 최신화 성숙도 모델에서 어느 위치에 있는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b6a5-110">Figure 4-1 highlights how Cloud-Optimized apps are positioned in Azure application modernization maturity models.</span></span>

![클라우드 최적화 응용 프로그램의 위치](./media/image1.png)

> <span data-ttu-id="6b6a5-112">**그림 4-1.**</span><span class="sxs-lookup"><span data-stu-id="6b6a5-112">**Figure 4-1.**</span></span> <span data-ttu-id="6b6a5-113">클라우드 최적화 응용 프로그램의 위치</span><span class="sxs-lookup"><span data-stu-id="6b6a5-113">Positioning Cloud-Optimized applications</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6b6a5-114">[이전](../migrate-your-relational-databases-to-azure.md)
>[다음](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6b6a5-114">[Previous](../migrate-your-relational-databases-to-azure.md)
[Next](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)</span></span>