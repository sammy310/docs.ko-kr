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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ccc45482f691d9950c641ef126a657052a280e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213640"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="39098-102">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39098-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="39098-103">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="39098-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39098-104">메서드</span><span class="sxs-lookup"><span data-stu-id="39098-104">Methods</span></span>  
  
|<span data-ttu-id="39098-105">메서드</span><span class="sxs-lookup"><span data-stu-id="39098-105">Method</span></span>|<span data-ttu-id="39098-106">설명</span><span class="sxs-lookup"><span data-stu-id="39098-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39098-107">SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="39098-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="39098-108">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39098-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39098-109">설명</span><span class="sxs-lookup"><span data-stu-id="39098-109">Remarks</span></span>  
 <span data-ttu-id="39098-110">이 인터페이스는 ICorDebugProcess 및 ICorDebugProcess2 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="39098-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39098-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39098-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39098-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39098-112">Requirements</span></span>  
 <span data-ttu-id="39098-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="39098-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39098-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39098-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39098-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39098-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="39098-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="39098-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39098-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="39098-117">See also</span></span>

- [<span data-ttu-id="39098-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39098-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="39098-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="39098-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
