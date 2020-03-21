---
title: GetCORSystemDirectory 함수
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178200"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="5f40c-102">GetCORSystemDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="5f40c-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="5f40c-103">프로세스에 로드되는 공통 언어 런타임(CLR)의 설치 디렉토리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="5f40c-104">설치 디렉토리는 "c:\windows\microsoft.net\framework\v1.0.3705"와 같은 자격을 갖추게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="5f40c-105">이 함수는 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-105">This function is deprecated.</span></span> <span data-ttu-id="5f40c-106">.NET 프레임워크 4에 제공된 [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) 메서드로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f40c-107">구문</span><span class="sxs-lookup"><span data-stu-id="5f40c-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5f40c-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f40c-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="5f40c-109">【아웃】 런타임이 프로세스에 로드된 런타임에 대해 설치 디렉터리의 정규화된 이름을 포함하는 문자열을 반환하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="5f40c-110">런타임이 아직 프로세스에 로드되지 않은 경우 함수는 컴퓨터에 설치된 최신 버전의 런타임에 대한 적절한 디렉터리 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5f40c-111">【인】 의 크기(바이트)입니다. `pbuffer`</span><span class="sxs-lookup"><span data-stu-id="5f40c-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5f40c-112">【아웃】 에서 반환된 문자 `pbuffer`수입니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f40c-113">설명</span><span class="sxs-lookup"><span data-stu-id="5f40c-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5f40c-114">CLR의 버전 4를 실행하는 프로세스에서는 이 함수를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5f40c-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="5f40c-115">컴퓨터에 이전 버전의 CLR이 설치된 경우 이 함수는 해당 버전에 대한 설치 디렉터리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f40c-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f40c-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f40c-116">Requirements</span></span>  
 <span data-ttu-id="5f40c-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f40c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f40c-118">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="5f40c-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f40c-119">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f40c-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f40c-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f40c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f40c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f40c-121">See also</span></span>

- [<span data-ttu-id="5f40c-122">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="5f40c-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
