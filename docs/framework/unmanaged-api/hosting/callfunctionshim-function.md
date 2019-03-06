---
title: CallFunctionShim 함수
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44f343fa6d9f620145c707e5987ecaedf17dcba8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478988"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="94b4a-102">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="94b4a-102">CallFunctionShim Function</span></span>
<span data-ttu-id="94b4a-103">지정한 이름 및 매개 변수는 지정 된 라이브러리에 있는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="94b4a-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b4a-105">구문</span><span class="sxs-lookup"><span data-stu-id="94b4a-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94b4a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94b4a-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="94b4a-107">[in] 함수를 포함 하는 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="94b4a-108">[in] 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="94b4a-109">[in] 함수에 전달할 첫 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="94b4a-110">[in] 함수에 전달할 두 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="94b4a-111">[in] 함수가 포함 된 라이브러리의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="94b4a-112">[in] 사용 하도록 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-112">[in] Reserved for future use.</span></span> <span data-ttu-id="94b4a-113">이 매개 변수에 0을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4a-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94b4a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94b4a-114">Requirements</span></span>  
 <span data-ttu-id="94b4a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="94b4a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94b4a-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94b4a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94b4a-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94b4a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94b4a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94b4a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b4a-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="94b4a-119">See also</span></span>
- [<span data-ttu-id="94b4a-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="94b4a-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
