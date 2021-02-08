---
description: '자세히 알아보기: CorDebugCodeInvokePurpose 열거형'
title: CorDebugCodeInvokePurpose 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: 1402343cc15e451975567564e6ce353900454bf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801724"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="9ec06-103">CorDebugCodeInvokePurpose 열거형</span><span class="sxs-lookup"><span data-stu-id="9ec06-103">CorDebugCodeInvokePurpose Enumeration</span></span>

<span data-ttu-id="9ec06-104">내보낸 함수가 관리 코드를 호출하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-104">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec06-105">구문</span><span class="sxs-lookup"><span data-stu-id="9ec06-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="9ec06-106">구성원</span><span class="sxs-lookup"><span data-stu-id="9ec06-106">Members</span></span>  
  
|<span data-ttu-id="9ec06-107">멤버</span><span class="sxs-lookup"><span data-stu-id="9ec06-107">Member</span></span>|<span data-ttu-id="9ec06-108">설명</span><span class="sxs-lookup"><span data-stu-id="9ec06-108">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="9ec06-109">없음 또는 알 수 없음.</span><span class="sxs-lookup"><span data-stu-id="9ec06-109">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="9ec06-110">관리 코드는 역방향 p-invoke 등의 관리되는 진입점을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-110">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="9ec06-111">그보다 자세한 용도는 런타임에서 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-111">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="9ec06-112">관리 코드가 정적 생성자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-112">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="9ec06-113">관리 코드가 호출된 일부 인터페이스 메서드에 대한 구현을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-113">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ec06-114">설명</span><span class="sxs-lookup"><span data-stu-id="9ec06-114">Remarks</span></span>  

 <span data-ttu-id="9ec06-115">이 열거형은 [ICorDebugProcess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) 메서드에서 관리 코드를 단계별로 실행 하는 방법에 대 한 정보를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-115">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ec06-116">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec06-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ec06-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ec06-117">Requirements</span></span>  

 <span data-ttu-id="9ec06-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ec06-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ec06-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ec06-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ec06-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ec06-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ec06-121">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ec06-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec06-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ec06-122">See also</span></span>

- [<span data-ttu-id="9ec06-123">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="9ec06-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="9ec06-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="9ec06-124">Debugging</span></span>](index.md)
