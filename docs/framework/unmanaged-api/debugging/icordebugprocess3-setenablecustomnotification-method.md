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
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212128"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="7c90f-102">ICorDebugProcess3::SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="7c90f-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="7c90f-103">지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c90f-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c90f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c90f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c90f-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="7c90f-106">진행 사용자 지정 디버거 알림을 지정 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="7c90f-107">[in] `true` 사용자 지정 디버거 알림을 사용 하려면 `false`알림을 사용 하지 않도록 설정 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="7c90f-108">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c90f-109">설명</span><span class="sxs-lookup"><span data-stu-id="7c90f-109">Remarks</span></span>  
 <span data-ttu-id="7c90f-110">`fEnable`가로 설정 되 면 `true` 메서드를 호출할 때 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> [ICorDebugManagedCallback3:: customnotification](icordebugmanagedcallback3-customnotification-method.md) 콜백이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="7c90f-111">알림은 기본적으로 사용 하지 않도록 설정 되어 있습니다. 따라서 디버거가 인식 하 고 처리 하려는 알림 유형을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="7c90f-112">[ICorDebugClass](icordebug-interface.md) 클래스의 범위는 응용 프로그램 도메인에 따라 결정 되기 때문에 디버거는 `SetEnableCustomNotification` 전체 프로세스에서 알림을 받으려는 경우 프로세스의 모든 응용 프로그램 도메인에 대해를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="7c90f-113">.NET Framework 4부터 유일 하 게 지원 되는 알림은 크로스 스레드 종속성 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="7c90f-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c90f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c90f-114">Requirements</span></span>  
 <span data-ttu-id="7c90f-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c90f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c90f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c90f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c90f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c90f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c90f-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c90f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c90f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c90f-119">See also</span></span>

- [<span data-ttu-id="7c90f-120">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c90f-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="7c90f-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c90f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7c90f-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="7c90f-122">Debugging</span></span>](index.md)
