---
description: '자세히 알아보기: ICorPublish 인터페이스'
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
ms.openlocfilehash: 0cec1d3407246989c6b916ca0760e6f556566ce6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721829"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="b96c6-103">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b96c6-103">ICorPublish Interface</span></span>

<span data-ttu-id="b96c6-104">프로세스에 대 한 정보를 게시 하 고 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하기 위한 일반 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b96c6-104">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b96c6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b96c6-105">Methods</span></span>  
  
|<span data-ttu-id="b96c6-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b96c6-106">Method</span></span>|<span data-ttu-id="b96c6-107">설명</span><span class="sxs-lookup"><span data-stu-id="b96c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b96c6-108">EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="b96c6-108">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="b96c6-109">이 컴퓨터에서 실행 되는 관리 되는 프로세스를 포함 하는 [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b96c6-109">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="b96c6-110">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="b96c6-110">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="b96c6-111">지정 된 식별자를 사용 하 여 프로세스를 나타내는 [ICorPublishProcess](icorpublishprocess-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b96c6-111">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b96c6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b96c6-112">Requirements</span></span>  

 <span data-ttu-id="b96c6-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b96c6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b96c6-114">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b96c6-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b96c6-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b96c6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b96c6-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b96c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96c6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b96c6-117">See also</span></span>

- [<span data-ttu-id="b96c6-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b96c6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b96c6-119">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="b96c6-119">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
