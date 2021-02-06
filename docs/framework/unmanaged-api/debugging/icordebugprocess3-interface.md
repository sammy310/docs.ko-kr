---
description: '자세히 알아보기: ICorDebugProcess3 인터페이스'
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
ms.openlocfilehash: 28b588bb4718f841e78b89ce44821971800b1f6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649977"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="ae045-103">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae045-103">ICorDebugProcess3 Interface</span></span>

<span data-ttu-id="ae045-104">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ae045-104">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae045-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae045-105">Methods</span></span>  
  
|<span data-ttu-id="ae045-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ae045-106">Method</span></span>|<span data-ttu-id="ae045-107">설명</span><span class="sxs-lookup"><span data-stu-id="ae045-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae045-108">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="ae045-108">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="ae045-109">지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae045-109">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae045-110">설명</span><span class="sxs-lookup"><span data-stu-id="ae045-110">Remarks</span></span>  

 <span data-ttu-id="ae045-111">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae045-111">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae045-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae045-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae045-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae045-113">Requirements</span></span>  

 <span data-ttu-id="ae045-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae045-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae045-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae045-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae045-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae045-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae045-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae045-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae045-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae045-118">See also</span></span>

- [<span data-ttu-id="ae045-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae045-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ae045-120">디버깅</span><span class="sxs-lookup"><span data-stu-id="ae045-120">Debugging</span></span>](index.md)
