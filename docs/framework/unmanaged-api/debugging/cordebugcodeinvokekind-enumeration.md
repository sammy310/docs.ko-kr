---
description: '자세히 알아보기: CorDebugCodeInvokeKind 열거형'
title: CorDebugCodeInvokeKind 열거형
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: d3fc3fe6f7568adcb2d1bbbe18c98d9d84bac337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747090"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="02975-103">CorDebugCodeInvokeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="02975-103">CorDebugCodeInvokeKind Enumeration</span></span>

<span data-ttu-id="02975-104">내보낸 함수가 관리 코드를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02975-104">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02975-105">구문</span><span class="sxs-lookup"><span data-stu-id="02975-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,
    CODE_INVOKE_KIND_RETURN,
    CODE_INVOKE_KIND_TAILCALL,
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="02975-106">구성원</span><span class="sxs-lookup"><span data-stu-id="02975-106">Members</span></span>  
  
|<span data-ttu-id="02975-107">멤버</span><span class="sxs-lookup"><span data-stu-id="02975-107">Member</span></span>|<span data-ttu-id="02975-108">설명</span><span class="sxs-lookup"><span data-stu-id="02975-108">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="02975-109">이 메서드가 관리 코드를 호출하는 경우 나중에 명시적 이벤트 또는 중단점을 사용하여 해당 코드를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02975-109">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="02975-110">-- 또는 --</span><span class="sxs-lookup"><span data-stu-id="02975-110">--or--</span></span><br /><br /> <span data-ttu-id="02975-111">이 메서드를 쉽게 중지할 수 있는 방법이 없어 해당 메서드가 호출하는 일부 관리 코드가 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02975-111">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="02975-112">-- 또는 --</span><span class="sxs-lookup"><span data-stu-id="02975-112">--or--</span></span><br /><br /> <span data-ttu-id="02975-113">메서드가 관리 코드를 호출하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02975-113">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="02975-114">이 메서드는 반환 명령을 통해 관리 코드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02975-114">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="02975-115">단계별 실행 시 다음 관리 코드에 도달하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02975-115">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="02975-116">이 메서드는 마무리 호출을 통해 관리 코드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="02975-116">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="02975-117">호출 명령을 한 단계씩/프로시저 단위로 실행하면 관리 코드에 도달하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02975-117">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02975-118">설명</span><span class="sxs-lookup"><span data-stu-id="02975-118">Remarks</span></span>  

 <span data-ttu-id="02975-119">이 열거형은 [ICorDebugProcess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) 메서드에서 관리 코드를 단계별로 실행 하는 방법에 대 한 정보를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02975-119">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02975-120">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02975-120">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02975-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02975-121">Requirements</span></span>  

 <span data-ttu-id="02975-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02975-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02975-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02975-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02975-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02975-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02975-125">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02975-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02975-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02975-126">See also</span></span>

- [<span data-ttu-id="02975-127">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="02975-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="02975-128">디버깅</span><span class="sxs-lookup"><span data-stu-id="02975-128">Debugging</span></span>](index.md)
