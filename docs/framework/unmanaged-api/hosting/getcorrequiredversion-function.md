---
description: '자세한 정보: GetCORRequiredVersion 함수'
title: GetCORRequiredVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
ms.openlocfilehash: ea1b928054e3ec6080b00e2a41228035f50c0f84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785356"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="671da-103">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="671da-103">GetCORRequiredVersion Function</span></span>

<span data-ttu-id="671da-104">필요한 CLR (공용 언어 런타임) 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="671da-104">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="671da-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="671da-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="671da-106">구문</span><span class="sxs-lookup"><span data-stu-id="671da-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="671da-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="671da-107">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="671da-108">제한이 버전 번호를 지정 하는 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="671da-108">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="671da-109">진행 버퍼의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="671da-109">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="671da-110">제한이 버퍼에서 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="671da-110">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="671da-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="671da-111">Requirements</span></span>  

 <span data-ttu-id="671da-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="671da-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="671da-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="671da-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="671da-114">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="671da-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="671da-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="671da-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671da-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="671da-116">See also</span></span>

- [<span data-ttu-id="671da-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="671da-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
