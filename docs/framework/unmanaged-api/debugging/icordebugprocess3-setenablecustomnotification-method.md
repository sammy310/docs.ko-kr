---
description: '자세히 알아보기: ICorDebugProcess3:: SetEnableCustomNotification 메서드'
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
ms.openlocfilehash: 71d1d23b1fa4ba16b26b7c9bacf7fb5cec5e5074
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746476"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="51513-103">ICorDebugProcess3::SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="51513-103">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>

<span data-ttu-id="51513-104">지정 된 형식의 사용자 지정 디버거 알림을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51513-104">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51513-105">구문</span><span class="sxs-lookup"><span data-stu-id="51513-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51513-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51513-106">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="51513-107">진행 사용자 지정 디버거 알림을 지정 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51513-107">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="51513-108">[in] `true` 사용자 지정 디버거 알림을 사용 하려면 `false` 알림을 사용 하지 않도록 설정 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="51513-108">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="51513-109">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="51513-109">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51513-110">설명</span><span class="sxs-lookup"><span data-stu-id="51513-110">Remarks</span></span>  

 <span data-ttu-id="51513-111">`fEnable`가로 설정 되 면 `true` 메서드를 호출할 때 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> [ICorDebugManagedCallback3:: customnotification](icordebugmanagedcallback3-customnotification-method.md) 콜백이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="51513-111">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="51513-112">알림은 기본적으로 사용 하지 않도록 설정 되어 있습니다. 따라서 디버거가 인식 하 고 처리 하려는 알림 유형을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51513-112">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="51513-113">[ICorDebugClass](icordebug-interface.md) 클래스의 범위는 응용 프로그램 도메인에 따라 결정 되기 때문에 디버거는 `SetEnableCustomNotification` 전체 프로세스에서 알림을 받으려는 경우 프로세스의 모든 응용 프로그램 도메인에 대해를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51513-113">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="51513-114">.NET Framework 4부터 유일 하 게 지원 되는 알림은 크로스 스레드 종속성 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="51513-114">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51513-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51513-115">Requirements</span></span>  

 <span data-ttu-id="51513-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51513-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51513-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51513-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51513-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51513-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51513-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51513-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51513-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51513-120">See also</span></span>

- [<span data-ttu-id="51513-121">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51513-121">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="51513-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51513-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="51513-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="51513-123">Debugging</span></span>](index.md)
