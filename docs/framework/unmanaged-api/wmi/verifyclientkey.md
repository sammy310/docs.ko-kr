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
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783083"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="a07c9-103">VerifyClientKey 함수</span><span class="sxs-lookup"><span data-stu-id="a07c9-103">VerifyClientKey function</span></span>
<span data-ttu-id="a07c9-104">클라이언트 키가 올바른 보안을 유지하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a07c9-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a07c9-105">구문</span><span class="sxs-lookup"><span data-stu-id="a07c9-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="a07c9-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="a07c9-106">Return value</span></span>

<span data-ttu-id="a07c9-107">함수가 성공할 경우 반환 값은 `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="a07c9-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="a07c9-108">반환 값은 0이 아닌 오류 코드에 정의 된 함수가 실패 한 경우 *WinError.h*합니다.</span><span class="sxs-lookup"><span data-stu-id="a07c9-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="a07c9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a07c9-109">Requirements</span></span>  
 <span data-ttu-id="a07c9-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a07c9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a07c9-111">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="a07c9-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="a07c9-112">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a07c9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a07c9-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a07c9-113">See also</span></span>

- [<span data-ttu-id="a07c9-114">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a07c9-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
