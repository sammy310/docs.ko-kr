---
title: ICorDebugProcess3::SetEnableCustomNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58e50a0c02f15590e5bbbcadaabeaa7e3886b74b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736823"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="00a0f-102">ICorDebugProcess3::SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="00a0f-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="00a0f-103">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="00a0f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00a0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00a0f-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="00a0f-106">[in] 사용자 지정 디버거 알림을 지정 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="00a0f-107">[in] `true` 사용자 지정 디버거 알림을;를 사용 하도록 설정 하려면 `false` 알림을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="00a0f-108">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00a0f-109">설명</span><span class="sxs-lookup"><span data-stu-id="00a0f-109">Remarks</span></span>  
 <span data-ttu-id="00a0f-110">때 `fEnable` 로 설정 되어 `true`를 호출 합니다 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드 트리거는 [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="00a0f-111">알림이는 기본적으로 비활성화 됩니다. 따라서 디버거 인식 하 고 처리 하려는 모든 알림 유형을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="00a0f-112">때문에 합니다 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 클래스는 응용 프로그램 도메인으로 범위가 지정 되며, 디버거를 호출 해야 `SetEnableCustomNotification` 전체 프로세스에서 알림을 받으려는 경우 프로세스에 있는 모든 응용 프로그램 도메인에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="00a0f-113">.NET Framework 4부터만 지원 되는 알림은 크로스 스레드 종속성 알림이입니다.</span><span class="sxs-lookup"><span data-stu-id="00a0f-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a0f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00a0f-114">Requirements</span></span>  
 <span data-ttu-id="00a0f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00a0f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a0f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00a0f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00a0f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a0f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a0f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a0f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a0f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="00a0f-119">See also</span></span>

- [<span data-ttu-id="00a0f-120">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00a0f-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="00a0f-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00a0f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="00a0f-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="00a0f-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
