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
ms.openlocfilehash: f197c8802bd9e55391b3e3e20c64398736070a16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136331"
---
# <a name="getfileversion-function"></a><span data-ttu-id="1141e-102">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="1141e-102">GetFileVersion Function</span></span>
<span data-ttu-id="1141e-103">지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="1141e-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1141e-105">구문</span><span class="sxs-lookup"><span data-stu-id="1141e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1141e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1141e-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="1141e-107">진행 검사할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1141e-108">[in, out] 반환 되는 버전 정보에 할당 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="1141e-109">진행 `szBuffer`의 크기 (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="1141e-110">제한이 반환 된 `szBuffer`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="1141e-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1141e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1141e-111">Requirements</span></span>  
 <span data-ttu-id="1141e-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1141e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1141e-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1141e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1141e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1141e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1141e-115">참조</span><span class="sxs-lookup"><span data-stu-id="1141e-115">See also</span></span>

- [<span data-ttu-id="1141e-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1141e-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
