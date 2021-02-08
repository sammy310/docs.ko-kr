---
description: '자세한 정보: WCF에 필요한 운영 체제 리소스'
title: WCF에 필요한 운영 체제 리소스
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 717ab2074c0dcf840919c2bd8afa2641e106ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779220"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="ab8b2-103">WCF에 필요한 운영 체제 리소스</span><span class="sxs-lookup"><span data-stu-id="ab8b2-103">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="ab8b2-104">WCF (Windows Communication Foundation)는 작동 하기 위해 운영 체제에서 제공 하는 여러 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ab8b2-104">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="ab8b2-105">다음 표에서는 이러한 리소스를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8b2-105">The following table lists those resources:</span></span>

|<span data-ttu-id="ab8b2-106">리소스</span><span class="sxs-lookup"><span data-stu-id="ab8b2-106">Resource</span></span>|<span data-ttu-id="ab8b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="ab8b2-107">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="ab8b2-108">MSDTC(Microsoft Distributed Transaction Coordinator)</span><span class="sxs-lookup"><span data-stu-id="ab8b2-108">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="ab8b2-109">OleTx 트랜잭션을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8b2-109">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="ab8b2-110">IIS(인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="ab8b2-110">Internet Information Services (IIS)</span></span>|<span data-ttu-id="ab8b2-111">IIS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8b2-111">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="ab8b2-112">WAS(Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="ab8b2-112">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="ab8b2-113">WAS를 사용하여 애플리케이션을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab8b2-113">Required if you want to use WAS to host your application.</span></span>|
