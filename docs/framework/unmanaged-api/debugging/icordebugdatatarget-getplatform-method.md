---
title: ICorDebugDataTarget::GetPlatform 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0769f30b6ac166e065fb6299c61c1e71e402c49
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607049"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="2ad5d-102">ICorDebugDataTarget::GetPlatform 메서드</span><span class="sxs-lookup"><span data-stu-id="2ad5d-102">ICorDebugDataTarget::GetPlatform Method</span></span>
<span data-ttu-id="2ad5d-103">프로세서 아키텍처와 대상 프로세스가 실행 되는 운영 체제를 포함 하 여 플랫폼에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ad5d-104">Syntax</span></span>  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ad5d-105">Parameters</span></span>  
 `pTargetPlatform`  
 <span data-ttu-id="2ad5d-106">[out] 에 대 한 포인터를 [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) 대상 플랫폼을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-106">[out] A pointer to a [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ad5d-107">설명</span><span class="sxs-lookup"><span data-stu-id="2ad5d-107">Remarks</span></span>  
 <span data-ttu-id="2ad5d-108">`CorDebugPlatformEnum` 열거형 반환 값은 사용 된 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 포인터 크기, 주소 공간 레이아웃, 레지스터 집합, 명령 형식, 상황에 맞는 레이아웃 대상 프로세스의 세부 정보를 확인 하는 인터페이스 및 호출 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="2ad5d-109">`pTargetPlatform` 값 사용에는 실제 하드웨어를 지정 하는 대신 대상에 대해 에뮬레이트 되는 플랫폼을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="2ad5d-110">예를 들어, 64 비트 버전 Windows 운영 체제의 Windows (WOW) 환경에서 Windows에서 실행 중인 프로세스를 사용 해야 합니다 `CORDB_PLATFORM_WINDOWS_X86` 의 값을 [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="2ad5d-111">이 메서드는 성공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-111">This method must succeed.</span></span> <span data-ttu-id="2ad5d-112">실패 한 경우 대상 플랫폼을 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="2ad5d-113">메서드는 다음과 같은 이유로 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="2ad5d-114">대상에 대해 에뮬레이트 되는 플랫폼을 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="2ad5d-115">대상 플랫폼에는 실제 하드웨어를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad5d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ad5d-116">Requirements</span></span>  
 <span data-ttu-id="2ad5d-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2ad5d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad5d-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ad5d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ad5d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ad5d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ad5d-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad5d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad5d-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ad5d-121">See also</span></span>

- [<span data-ttu-id="2ad5d-122">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ad5d-122">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="2ad5d-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ad5d-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2ad5d-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="2ad5d-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
