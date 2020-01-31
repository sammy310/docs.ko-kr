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
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790719"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="961e1-102">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="961e1-102">ICorPublish Interface</span></span>
<span data-ttu-id="961e1-103">프로세스에 대 한 정보를 게시 하 고 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하기 위한 일반 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="961e1-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="961e1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="961e1-104">Methods</span></span>  
  
|<span data-ttu-id="961e1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="961e1-105">Method</span></span>|<span data-ttu-id="961e1-106">설명</span><span class="sxs-lookup"><span data-stu-id="961e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="961e1-107">EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="961e1-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="961e1-108">이 컴퓨터에서 실행 되는 관리 되는 프로세스를 포함 하는 [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="961e1-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="961e1-109">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="961e1-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="961e1-110">지정 된 식별자를 사용 하 여 프로세스를 나타내는 [ICorPublishProcess](icorpublishprocess-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="961e1-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="961e1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="961e1-111">Requirements</span></span>  
 <span data-ttu-id="961e1-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="961e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961e1-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="961e1-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="961e1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="961e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="961e1-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961e1-116">참조</span><span class="sxs-lookup"><span data-stu-id="961e1-116">See also</span></span>

- [<span data-ttu-id="961e1-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="961e1-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="961e1-118">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="961e1-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
