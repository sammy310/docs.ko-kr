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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121790"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="e1a6d-102">ICorPublish::EnumProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="e1a6d-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="e1a6d-103">이 컴퓨터에서 실행 되는 관리 되는 프로세스의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1a6d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1a6d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1a6d-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="e1a6d-106">검색할 프로세스의 유형을 지정 하는 [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="e1a6d-107">현재 버전에서는 COR_PUB_MANAGEDONLY만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="e1a6d-108">프로세스의 열거자 인 [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1a6d-109">주의</span><span class="sxs-lookup"><span data-stu-id="e1a6d-109">Remarks</span></span>  
 <span data-ttu-id="e1a6d-110">열거자의 프로세스 컬렉션은 `EnumProcesses` 메서드가 호출 될 때 실행 중인 프로세스의 스냅숏을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="e1a6d-111">열거자에는 `EnumProcesses`를 호출한 후 종료 하거나 시작 하는 프로세스가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="e1a6d-112">이 [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) 인스턴스에서 `EnumProcesses` 메서드를 두 번 이상 호출 하 여 새로운 최신 프로세스 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="e1a6d-113">기존 컬렉션은 `EnumProcesses` 메서드에 대 한 후속 호출의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a6d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1a6d-114">Requirements</span></span>  
 <span data-ttu-id="e1a6d-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1a6d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a6d-116">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e1a6d-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e1a6d-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a6d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a6d-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a6d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a6d-119">참조</span><span class="sxs-lookup"><span data-stu-id="e1a6d-119">See also</span></span>

- [<span data-ttu-id="e1a6d-120">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a6d-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
