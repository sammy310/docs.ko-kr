---
title: ICorPublish::EnumProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116297"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="ff91a-102">ICorPublish::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="ff91a-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="ff91a-103">이 컴퓨터에서 실행 되는 관리 되는 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff91a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff91a-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff91a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff91a-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="ff91a-106">값을 [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) 검색 해야 하는 프로세스의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="ff91a-107">현재 버전에서는 COR_PUB_MANAGEDONLY만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="ff91a-108">주소에 대 한 포인터를 [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) 인스턴스 프로세스의 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff91a-109">설명</span><span class="sxs-lookup"><span data-stu-id="ff91a-109">Remarks</span></span>  
 <span data-ttu-id="ff91a-110">프로세스의 열거자의 컬렉션은 스냅숏을 기반으로 실행 하는 경우 프로세스의는 `EnumProcesses` 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="ff91a-111">열거자는 종료 하기 전에 또는 후에 시작 하는 모든 프로세스를 포함 하지 것입니다 `EnumProcesses` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="ff91a-112">합니다 `EnumProcesses` 이 메서드를 두 번 이상 호출할 수 있습니다 [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) 인스턴스 프로세스의 새 최신 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff91a-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="ff91a-113">기존 컬렉션의 후속 호출에 의해 적용 되지 것입니다는 `EnumProcesses` 메서드.</span><span class="sxs-lookup"><span data-stu-id="ff91a-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff91a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff91a-114">Requirements</span></span>  
 <span data-ttu-id="ff91a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff91a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff91a-116">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ff91a-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ff91a-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff91a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff91a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff91a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff91a-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff91a-119">See also</span></span>

- [<span data-ttu-id="ff91a-120">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff91a-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
