---
title: ICorPublish 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076343"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="29570-102">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29570-102">ICorPublish Interface</span></span>
<span data-ttu-id="29570-103">해당 프로세스의 프로세스에 대 한 정보 및 응용 프로그램 도메인에 대 한 정보를 게시 하는 것에 대 한 일반적인 인터페이스로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="29570-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29570-104">메서드</span><span class="sxs-lookup"><span data-stu-id="29570-104">Methods</span></span>  
  
|<span data-ttu-id="29570-105">메서드</span><span class="sxs-lookup"><span data-stu-id="29570-105">Method</span></span>|<span data-ttu-id="29570-106">설명</span><span class="sxs-lookup"><span data-stu-id="29570-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29570-107">EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="29570-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="29570-108">가져옵니다는 [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) 이 컴퓨터에서 실행 되는 관리 되는 프로세스를 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="29570-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="29570-109">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="29570-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="29570-110">가져옵니다는 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 지정된 된 식별자를 사용 하 여 프로세스를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="29570-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29570-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29570-111">Requirements</span></span>  
 <span data-ttu-id="29570-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29570-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29570-113">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="29570-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="29570-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29570-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29570-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29570-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29570-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="29570-116">See also</span></span>

- [<span data-ttu-id="29570-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29570-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="29570-118">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="29570-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
