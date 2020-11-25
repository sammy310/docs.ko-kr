---
title: ICorPublish::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: a45f613b7547e2e80abdbd8ac85cb0b2b6a499e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716891"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="bd6f3-102">ICorPublish::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="bd6f3-102">ICorPublish::GetProcess Method</span></span>

<span data-ttu-id="bd6f3-103">지정 된 식별자를 사용 하 여 프로세스를 나타내는 [ICorPublishProcess](icorpublishprocess-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd6f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd6f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd6f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd6f3-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="bd6f3-106">진행 프로세스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bd6f3-107">제한이 프로세스를 나타내는 인스턴스의 주소에 대 한 포인터 `ICorPublishProcess` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd6f3-108">설명</span><span class="sxs-lookup"><span data-stu-id="bd6f3-108">Remarks</span></span>  

 <span data-ttu-id="bd6f3-109">`GetProcess` 프로세스가 없거나 현재 사용자가 디버깅할 수 있는 관리 되는 프로세스가 아닌 경우 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd6f3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd6f3-110">Requirements</span></span>  

 <span data-ttu-id="bd6f3-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd6f3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd6f3-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="bd6f3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bd6f3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd6f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd6f3-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd6f3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd6f3-115">참조</span><span class="sxs-lookup"><span data-stu-id="bd6f3-115">See also</span></span>

- [<span data-ttu-id="bd6f3-116">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd6f3-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
