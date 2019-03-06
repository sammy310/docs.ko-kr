---
title: GetFileVersion 함수
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 214f16f970cfb2c319f3a26afc882e6102c1be71
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498265"
---
# <a name="getfileversion-function"></a><span data-ttu-id="d3617-102">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d3617-102">GetFileVersion Function</span></span>
<span data-ttu-id="d3617-103">지정된 된 버퍼를 사용 하 여 지정된 된 파일의 공용 언어 런타임 (CLR) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="d3617-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3617-105">구문</span><span class="sxs-lookup"><span data-stu-id="d3617-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3617-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3617-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="d3617-107">[in] 검사할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d3617-108">[out에서] 반환 되는 버전 정보에 대 한 할당 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d3617-109">[in] 와이드 문자에서 크기의 `szBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d3617-110">[out] 반환 된 바이트의 크기, `szBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3617-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3617-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3617-111">Requirements</span></span>  
 <span data-ttu-id="d3617-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3617-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3617-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3617-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3617-114">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3617-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3617-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3617-115">See also</span></span>
- [<span data-ttu-id="d3617-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d3617-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
