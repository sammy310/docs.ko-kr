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
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679795"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="366e3-102">ICorDebugDataTarget::GetPlatform 메서드</span><span class="sxs-lookup"><span data-stu-id="366e3-102">ICorDebugDataTarget::GetPlatform Method</span></span>

<span data-ttu-id="366e3-103">대상 프로세스가 실행 되는 프로세서 아키텍처 및 운영 체제를 포함 하 여 플랫폼에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="366e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="366e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="366e3-105">Parameters</span></span>  

 `pTargetPlatform`  
 <span data-ttu-id="366e3-106">제한이 대상 플랫폼을 설명 하는 [Cordebugplatformenum](cordebugplatform-enumeration.md) 열거형에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-106">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="366e3-107">설명</span><span class="sxs-lookup"><span data-stu-id="366e3-107">Remarks</span></span>  

 <span data-ttu-id="366e3-108">`CorDebugPlatformEnum`열거형 반환 값은 [ICorDebug](icordebug-interface.md) 인터페이스에서 포인터 크기, 주소 공간 레이아웃, 레지스터 집합, 명령 형식, 컨텍스트 레이아웃 및 호출 규칙 등 대상 프로세스의 세부 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="366e3-109">이 `pTargetPlatform` 값은 사용 중인 실제 하드웨어를 지정 하는 대신 대상에 대해 에뮬레이트하는 플랫폼을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="366e3-110">예를 들어 Windows 운영 체제 64 비트 버전의 WOW (Windows on Windows) 환경에서 실행 되는 프로세스는 `CORDB_PLATFORM_WINDOWS_X86` [Cordebugplatformenum](cordebugplatform-enumeration.md) 열거형의 값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="366e3-111">이 메서드는 성공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-111">This method must succeed.</span></span> <span data-ttu-id="366e3-112">실패 한 경우 대상 플랫폼을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="366e3-113">메서드는 다음과 같은 이유로 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="366e3-114">대상에 대해 에뮬레이트하는 플랫폼을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="366e3-115">대상 플랫폼의 실제 하드웨어를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="366e3-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366e3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="366e3-116">Requirements</span></span>  

 <span data-ttu-id="366e3-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="366e3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366e3-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="366e3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="366e3-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="366e3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="366e3-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366e3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="366e3-121">참조</span><span class="sxs-lookup"><span data-stu-id="366e3-121">See also</span></span>

- [<span data-ttu-id="366e3-122">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="366e3-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="366e3-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="366e3-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="366e3-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="366e3-124">Debugging</span></span>](index.md)
