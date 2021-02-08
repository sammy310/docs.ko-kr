---
description: '자세히 알아보기: GetFileVersion 함수'
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
ms.openlocfilehash: 7de19484f2f8123d61eb94e6a5ae09f56a3b5541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785304"
---
# <a name="getfileversion-function"></a><span data-ttu-id="9ea78-103">GetFileVersion 함수</span><span class="sxs-lookup"><span data-stu-id="9ea78-103">GetFileVersion Function</span></span>

<span data-ttu-id="9ea78-104">지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ea78-104">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="9ea78-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea78-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea78-106">구문</span><span class="sxs-lookup"><span data-stu-id="9ea78-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ea78-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ea78-107">Parameters</span></span>  

 `szFilename`  
 <span data-ttu-id="9ea78-108">진행 검사할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea78-108">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="9ea78-109">[in, out] 반환 되는 버전 정보에 할당 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea78-109">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9ea78-110">진행 의 크기 (와이드 문자)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="9ea78-110">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9ea78-111">제한이 반환 된의 크기 (바이트)입니다 `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="9ea78-111">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea78-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ea78-112">Requirements</span></span>  

 <span data-ttu-id="9ea78-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ea78-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea78-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9ea78-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ea78-115">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea78-115">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea78-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ea78-116">See also</span></span>

- [<span data-ttu-id="9ea78-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="9ea78-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
