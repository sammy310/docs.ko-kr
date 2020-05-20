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
ms.openlocfilehash: e8945d40a3761ec51a73a8ae90ddc1d84ccab651
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616868"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="29a98-102">CallFunctionShim 함수</span><span class="sxs-lookup"><span data-stu-id="29a98-102">CallFunctionShim Function</span></span>
<span data-ttu-id="29a98-103">지정 된 라이브러리에서 지정 된 이름 및 매개 변수를 가진 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="29a98-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a98-105">구문</span><span class="sxs-lookup"><span data-stu-id="29a98-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="29a98-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29a98-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="29a98-107">진행 함수를 포함 하는 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="29a98-108">진행 함수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="29a98-109">진행 함수에 전달할 첫 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="29a98-110">진행 함수에 전달할 두 번째 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="29a98-111">진행 함수를 포함 하는 라이브러리의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="29a98-112">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-112">[in] Reserved for future use.</span></span> <span data-ttu-id="29a98-113">이 매개 변수에서 0을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a98-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29a98-114">Requirements</span></span>  
 <span data-ttu-id="29a98-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29a98-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29a98-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29a98-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29a98-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="29a98-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29a98-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a98-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29a98-119">See also</span></span>

- [<span data-ttu-id="29a98-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="29a98-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
