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
ms.openlocfilehash: ec60274648315c4fa38f3832d8d39c1a269956b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129701"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="d8055-102">ICorDebugProcess3::SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="d8055-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="d8055-103">지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8055-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8055-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8055-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8055-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="d8055-106">진행 사용자 지정 디버거 알림을 지정 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="d8055-107">[in] 사용자 지정 디버거 알림을 사용 하도록 설정 하는 `true` 알림을 사용 하지 않도록 설정 하려면 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="d8055-108">기본값은 `false`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8055-109">주의</span><span class="sxs-lookup"><span data-stu-id="d8055-109">Remarks</span></span>  
 <span data-ttu-id="d8055-110">`fEnable`을 `true`로 설정 하면 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드를 호출 하 여 [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 콜백을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="d8055-111">알림은 기본적으로 사용 하지 않도록 설정 되어 있습니다. 따라서 디버거가 인식 하 고 처리 하려는 알림 유형을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="d8055-112">[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 클래스의 범위는 응용 프로그램 도메인에 따라 결정 되기 때문에 디버거는 전체 프로세스에서 알림을 받으려는 경우 프로세스의 모든 응용 프로그램 도메인에 대해 `SetEnableCustomNotification`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="d8055-113">.NET Framework 4부터 유일 하 게 지원 되는 알림은 크로스 스레드 종속성 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="d8055-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8055-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8055-114">Requirements</span></span>  
 <span data-ttu-id="d8055-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8055-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8055-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8055-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8055-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8055-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8055-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8055-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8055-119">참조</span><span class="sxs-lookup"><span data-stu-id="d8055-119">See also</span></span>

- [<span data-ttu-id="d8055-120">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8055-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="d8055-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8055-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d8055-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="d8055-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
