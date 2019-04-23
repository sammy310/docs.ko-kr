---
title: VerifyClientKey 함수 (관리 되지 않는 API 참조)
description: VerifyClientKey 함수 클라이언트 키에 올바른 보안을 보장 합니다.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214717"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="7acd7-103">VerifyClientKey 함수</span><span class="sxs-lookup"><span data-stu-id="7acd7-103">VerifyClientKey function</span></span>
<span data-ttu-id="7acd7-104">클라이언트 키가 올바른 보안을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7acd7-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7acd7-105">구문</span><span class="sxs-lookup"><span data-stu-id="7acd7-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="7acd7-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="7acd7-106">Return value</span></span>

<span data-ttu-id="7acd7-107">함수가 성공할 경우 반환 값은 `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="7acd7-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="7acd7-108">반환 값은 0이 아닌 오류 코드에 정의 된 함수가 실패 한 경우 *WinError.h*합니다.</span><span class="sxs-lookup"><span data-stu-id="7acd7-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="7acd7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7acd7-109">Requirements</span></span>  
 <span data-ttu-id="7acd7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7acd7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7acd7-111">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="7acd7-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="7acd7-112">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7acd7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7acd7-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="7acd7-113">See also</span></span>

- [<span data-ttu-id="7acd7-114">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="7acd7-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
