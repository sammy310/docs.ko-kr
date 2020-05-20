---
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
ms.openlocfilehash: 6b9fd62102056a8d5f859ac913f4786f04c1df7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617245"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="f518e-102">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="f518e-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="f518e-103">필요한 CLR (공용 언어 런타임) 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f518e-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="f518e-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f518e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f518e-105">구문</span><span class="sxs-lookup"><span data-stu-id="f518e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f518e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f518e-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="f518e-107">제한이 버전 번호를 지정 하는 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f518e-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f518e-108">진행 버퍼의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="f518e-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f518e-109">제한이 버퍼에서 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f518e-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f518e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f518e-110">Requirements</span></span>  
 <span data-ttu-id="f518e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f518e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f518e-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f518e-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f518e-113">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f518e-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f518e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f518e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f518e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f518e-115">See also</span></span>

- [<span data-ttu-id="f518e-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f518e-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
