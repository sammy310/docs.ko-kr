---
description: '자세히 알아보기: ICorDebugManagedCallback:: UnloadClass 메서드'
title: ICorDebugManagedCallback::UnloadClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: b76caf39611b0f59c74b4ae47d167e6f232a6dbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660221"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="b8596-103">ICorDebugManagedCallback::UnloadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="b8596-103">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="b8596-104">클래스가 언로드되고 있음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b8596-104">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8596-105">구문</span><span class="sxs-lookup"><span data-stu-id="b8596-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8596-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8596-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="b8596-107">진행 클래스가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8596-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="b8596-108">진행 클래스를 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8596-108">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8596-109">설명</span><span class="sxs-lookup"><span data-stu-id="b8596-109">Remarks</span></span>  

 <span data-ttu-id="b8596-110">이 호출 후에는 클래스를 참조 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8596-110">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8596-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8596-111">Requirements</span></span>  

 <span data-ttu-id="b8596-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8596-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8596-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8596-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8596-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8596-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8596-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8596-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8596-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8596-116">See also</span></span>

- [<span data-ttu-id="b8596-117">LoadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="b8596-117">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="b8596-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8596-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
