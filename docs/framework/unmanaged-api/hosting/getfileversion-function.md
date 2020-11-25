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
ms.openlocfilehash: 57b30824c7849127f48d4da61872945366e7141e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733245"
---
# <a name="getfileversion-function"></a><span data-ttu-id="d5b4a-102">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="d5b4a-102">GetFileVersion Function</span></span>

<span data-ttu-id="d5b4a-103">지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5b4a-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="d5b4a-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5b4a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b4a-105">구문</span><span class="sxs-lookup"><span data-stu-id="d5b4a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b4a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5b4a-106">Parameters</span></span>  

 `szFilename`  
 <span data-ttu-id="d5b4a-107">진행 검사할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b4a-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d5b4a-108">[in, out] 반환 되는 버전 정보에 할당 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d5b4a-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d5b4a-109">진행 의 크기 (와이드 문자)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="d5b4a-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d5b4a-110">제한이 반환 된의 크기 (바이트)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="d5b4a-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b4a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5b4a-111">Requirements</span></span>  

 <span data-ttu-id="d5b4a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5b4a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b4a-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d5b4a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5b4a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b4a-115">참조</span><span class="sxs-lookup"><span data-stu-id="d5b4a-115">See also</span></span>

- [<span data-ttu-id="d5b4a-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="d5b4a-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
