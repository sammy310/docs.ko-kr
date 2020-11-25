---
title: FLockClrVersionCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: d18702a1bb15d2cc6c7b8577b91ed011e9bd0c05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733674"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="81ea0-102">FLockClrVersionCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="81ea0-102">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="81ea0-103">초기화가 시작 되거나 완료 되었음을 나타내기 위해 CLR (공용 언어 런타임)에서 호출 하는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="81ea0-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="81ea0-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ea0-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ea0-105">구문</span><span class="sxs-lookup"><span data-stu-id="81ea0-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="81ea0-106">설명</span><span class="sxs-lookup"><span data-stu-id="81ea0-106">Remarks</span></span>  

 <span data-ttu-id="81ea0-107">이 함수는 호스트에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ea0-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ea0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81ea0-108">Requirements</span></span>  

 <span data-ttu-id="81ea0-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81ea0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ea0-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="81ea0-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81ea0-111">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="81ea0-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="81ea0-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ea0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ea0-113">참조</span><span class="sxs-lookup"><span data-stu-id="81ea0-113">See also</span></span>

- [<span data-ttu-id="81ea0-114">LockClrVersion 함수</span><span class="sxs-lookup"><span data-stu-id="81ea0-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="81ea0-115">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="81ea0-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
