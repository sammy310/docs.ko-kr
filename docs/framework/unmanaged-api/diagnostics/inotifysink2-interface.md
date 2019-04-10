---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f5307ce00160bb4151a7559daac4724367c6497
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157781"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="53587-102">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53587-102">INotifySink2 Interface</span></span>
<span data-ttu-id="53587-103">싱크 알림 위한 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="53587-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53587-104">메서드</span><span class="sxs-lookup"><span data-stu-id="53587-104">Methods</span></span>  
  
|<span data-ttu-id="53587-105">메서드</span><span class="sxs-lookup"><span data-stu-id="53587-105">Method</span></span>|<span data-ttu-id="53587-106">설명</span><span class="sxs-lookup"><span data-stu-id="53587-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53587-107">OnSyncCallEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="53587-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="53587-108">호출을 시작 하면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53587-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="53587-109">OnSyncCallExit 메서드</span><span class="sxs-lookup"><span data-stu-id="53587-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="53587-110">호출을 종료할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53587-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="53587-111">OnSyncCallOut 메서드</span><span class="sxs-lookup"><span data-stu-id="53587-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="53587-112">이 호출 하는 경우 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53587-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="53587-113">OnSyncCallReturn 메서드</span><span class="sxs-lookup"><span data-stu-id="53587-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="53587-114">호출 반환 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53587-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53587-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53587-115">Requirements</span></span>  
 <span data-ttu-id="53587-116">**헤더:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="53587-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53587-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="53587-117">See also</span></span>

- [<span data-ttu-id="53587-118">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53587-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="53587-119">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53587-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="53587-120">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="53587-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
