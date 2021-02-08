---
description: '자세히 알아보기: INotifySink2 인터페이스'
title: INotifySink2 인터페이스
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
ms.openlocfilehash: 4d046c5566d9cb1641426f6a990f39449c33bc4d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800294"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="020fa-103">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="020fa-103">INotifySink2 Interface</span></span>

<span data-ttu-id="020fa-104">싱크 알림에 대 한 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="020fa-104">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="020fa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-105">Methods</span></span>  
  
|<span data-ttu-id="020fa-106">메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-106">Method</span></span>|<span data-ttu-id="020fa-107">설명</span><span class="sxs-lookup"><span data-stu-id="020fa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="020fa-108">OnSyncCallEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-108">OnSyncCallEnter Method</span></span>](inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="020fa-109">호출을 입력할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020fa-109">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="020fa-110">OnSyncCallExit 메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-110">OnSyncCallExit Method</span></span>](inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="020fa-111">호출을 종료할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020fa-111">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="020fa-112">OnSyncCallOut 메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-112">OnSyncCallOut Method</span></span>](inotifysink2-onsynccallout-method.md)|<span data-ttu-id="020fa-113">호출이 호출 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020fa-113">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="020fa-114">OnSyncCallReturn 메서드</span><span class="sxs-lookup"><span data-stu-id="020fa-114">OnSyncCallReturn Method</span></span>](inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="020fa-115">호출이 반환 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020fa-115">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="020fa-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="020fa-116">Requirements</span></span>  

 <span data-ttu-id="020fa-117">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="020fa-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020fa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="020fa-118">See also</span></span>

- [<span data-ttu-id="020fa-119">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="020fa-119">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="020fa-120">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="020fa-120">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="020fa-121">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="020fa-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
