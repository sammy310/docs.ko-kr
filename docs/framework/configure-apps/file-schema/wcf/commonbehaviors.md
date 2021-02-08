---
description: 다음에 대해 자세히 알아보세요. <commonBehaviors>
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 2fa7397a2833623728bcca286682178d1cf3e1df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802322"
---
# \<commonBehaviors>

<span data-ttu-id="c3dd6-102">`commonBehaviors` 섹션은 machine.config 파일에만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3dd6-102">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="c3dd6-103">이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dd6-103">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="c3dd6-104">각 컬렉션은 컴퓨터의 모든 WCF 끝점과 서비스에서 사용 하는 동작 요소를 각각 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dd6-104">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="c3dd6-105">`endpointBehaviors`에 정의된 동작은 클라이언트에만 적용되고 `serviceBehaviors`에 정의된 동작은 서비스에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3dd6-105">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="c3dd6-106">두 `commonBehaviors` 및 `behaviors` 섹션 모두에서 동작이 정의되는 경우 `behaviors` 섹션의 동작이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c3dd6-106">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
