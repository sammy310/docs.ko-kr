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
ms.openlocfilehash: 31d93ac427ec67726c9456d623aeb683c9029ccd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773767"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="8cb1f-102">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="8cb1f-102">CallFunctionShim Function</span></span>
<span data-ttu-id="8cb1f-103">지정한 이름 및 매개 변수는 지정 된 라이브러리에 있는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="8cb1f-104">.NET Framework 4에서이 함수에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="8cb1f-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cb1f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cb1f-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="8cb1f-107">[in] 함수를 포함 하는 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="8cb1f-108">[in] 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="8cb1f-109">[in] 함수에 전달할 첫 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="8cb1f-110">[in] 함수에 전달할 두 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="8cb1f-111">[in] 함수가 포함 된 라이브러리의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8cb1f-112">[in] 사용 하도록 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-112">[in] Reserved for future use.</span></span> <span data-ttu-id="8cb1f-113">이 매개 변수에 0을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb1f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cb1f-114">Requirements</span></span>  
 <span data-ttu-id="8cb1f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8cb1f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb1f-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8cb1f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cb1f-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cb1f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cb1f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb1f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb1f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cb1f-119">See also</span></span>

- [<span data-ttu-id="8cb1f-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="8cb1f-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
