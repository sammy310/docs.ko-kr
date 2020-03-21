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
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178175"
---
# <a name="getfileversion-function"></a><span data-ttu-id="d3a63-102">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d3a63-102">GetFileVersion Function</span></span>
<span data-ttu-id="d3a63-103">지정된 버퍼를 사용하여 지정된 파일의 공통 언어 런타임(CLR) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3a63-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="d3a63-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3a63-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a63-105">구문</span><span class="sxs-lookup"><span data-stu-id="d3a63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3a63-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3a63-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="d3a63-107">【인】 검사할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a63-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d3a63-108">【인, 아웃】 반환되는 버전 정보에 대해 할당된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a63-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d3a63-109">【인】 크기, 넓은 문자, `szBuffer`의 .</span><span class="sxs-lookup"><span data-stu-id="d3a63-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d3a63-110">【아웃】 반환된 `szBuffer`의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d3a63-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3a63-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3a63-111">Requirements</span></span>  
 <span data-ttu-id="d3a63-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3a63-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a63-113">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="d3a63-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3a63-114">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3a63-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a63-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3a63-115">See also</span></span>

- [<span data-ttu-id="d3a63-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d3a63-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
