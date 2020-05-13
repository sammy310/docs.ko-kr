---
title: ICorDebugProcess3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: 826736d2db7aa1e618a2e5fe0655cedad9556b17
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213441"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="85b2a-102">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85b2a-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="85b2a-103">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85b2a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="85b2a-104">Methods</span></span>  
  
|<span data-ttu-id="85b2a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="85b2a-105">Method</span></span>|<span data-ttu-id="85b2a-106">설명</span><span class="sxs-lookup"><span data-stu-id="85b2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85b2a-107">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="85b2a-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="85b2a-108">지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85b2a-109">설명</span><span class="sxs-lookup"><span data-stu-id="85b2a-109">Remarks</span></span>  
 <span data-ttu-id="85b2a-110">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85b2a-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85b2a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85b2a-112">Requirements</span></span>  
 <span data-ttu-id="85b2a-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85b2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b2a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85b2a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85b2a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85b2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85b2a-116">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85b2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b2a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85b2a-117">See also</span></span>

- [<span data-ttu-id="85b2a-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85b2a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="85b2a-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="85b2a-119">Debugging</span></span>](index.md)
