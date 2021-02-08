---
description: '자세한 정보: 4806-DiscoveryMessageWithInvalidRelatesToOrOperationCompleted'
title: 4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted
ms.date: 03/30/2017
ms.assetid: 19e9a660-25f3-4332-b716-a12a59f2cbbb
ms.openlocfilehash: 51c1dd9e4478f53098a8087cb4c2e2efdceeaa2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788386"
---
# <a name="4806---discoverymessagewithinvalidrelatestooroperationcompleted"></a><span data-ttu-id="2843f-103">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="2843f-103">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="2843f-104">속성</span><span class="sxs-lookup"><span data-stu-id="2843f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2843f-105">ID</span><span class="sxs-lookup"><span data-stu-id="2843f-105">ID</span></span>|<span data-ttu-id="2843f-106">4806</span><span class="sxs-lookup"><span data-stu-id="2843f-106">4806</span></span>|  
|<span data-ttu-id="2843f-107">키워드</span><span class="sxs-lookup"><span data-stu-id="2843f-107">Keywords</span></span>|<span data-ttu-id="2843f-108">검색</span><span class="sxs-lookup"><span data-stu-id="2843f-108">Discovery</span></span>|  
|<span data-ttu-id="2843f-109">Level</span><span class="sxs-lookup"><span data-stu-id="2843f-109">Level</span></span>|<span data-ttu-id="2843f-110">경고</span><span class="sxs-lookup"><span data-stu-id="2843f-110">Warning</span></span>|  
|<span data-ttu-id="2843f-111">채널</span><span class="sxs-lookup"><span data-stu-id="2843f-111">Channel</span></span>|<span data-ttu-id="2843f-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그</span><span class="sxs-lookup"><span data-stu-id="2843f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2843f-113">설명</span><span class="sxs-lookup"><span data-stu-id="2843f-113">Description</span></span>  

 <span data-ttu-id="2843f-114">이 이벤트는 해당 작업이 완료되었거나 relatesTo 값이 잘못되어 검색 메시지가 DiscoveryClient에서 삭제되었을 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="2843f-114">This event is emitted when the discovery message was dropped by the DiscoveryClient because either the corresponding operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2843f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="2843f-115">Message</span></span>  

 <span data-ttu-id="2843f-116">해당 %4 작업이 완료되었거나 relatesTo 값이 잘못되어 messageId='%2'이고 relatesTo='%3'인 %1 메시지가 DiscoveryClient에서 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2843f-116">A %1 message with messageId='%2' and relatesTo='%3' was dropped by the DiscoveryClient because either the corresponding %4 operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2843f-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2843f-117">Details</span></span>
