---
title: IDebuggerInfo::IsDebuggerAttached 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805330"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="cf527-102">IDebuggerInfo::IsDebuggerAttached 메서드</span><span class="sxs-lookup"><span data-stu-id="cf527-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="cf527-103">관리 되는 디버거가이 프로세스에 연결 되어 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf527-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf527-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf527-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf527-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf527-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="cf527-106">제한이 관리 되는 `true` 디버거가 프로세스에 연결 되어 있으면이 고, 그렇지 않으면 인 값에 대 한 포인터입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="cf527-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf527-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf527-107">Requirements</span></span>  
 <span data-ttu-id="cf527-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf527-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf527-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cf527-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf527-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf527-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf527-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf527-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf527-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf527-112">See also</span></span>

- [<span data-ttu-id="cf527-113">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf527-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
