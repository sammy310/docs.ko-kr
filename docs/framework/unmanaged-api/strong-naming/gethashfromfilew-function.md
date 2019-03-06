---
title: GetHashFromFileW 함수
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc69ab8b2d3565c49eeee09d8860c81ec8818fe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473861"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="1a613-102">GetHashFromFileW 함수</span><span class="sxs-lookup"><span data-stu-id="1a613-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="1a613-103">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="1a613-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-104">This function has been deprecated.</span></span> <span data-ttu-id="1a613-105">사용 된 [iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a613-106">구문</span><span class="sxs-lookup"><span data-stu-id="1a613-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="1a613-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a613-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="1a613-108">[in] 유니코드 해시 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1a613-109">[out에서] 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="1a613-110">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="1a613-111">경우 `piHashAlg` CALG_SHA-1은 사용 하는 기본 알고리즘 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1a613-112">[out] 생성된 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1a613-113">[in] 가리키는 버퍼의 최대 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1a613-114">[out] 크기 (바이트)의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a613-115">설명</span><span class="sxs-lookup"><span data-stu-id="1a613-115">Remarks</span></span>  
 <span data-ttu-id="1a613-116">이 함수는 동일 [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)파일 이름 사양이 ANSI 대신 유니코드는 점을 제외 하 고, 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a613-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a613-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a613-117">Requirements</span></span>  
 <span data-ttu-id="1a613-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a613-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a613-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1a613-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1a613-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1a613-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a613-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a613-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a613-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="1a613-122">See also</span></span>
- [<span data-ttu-id="1a613-123">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="1a613-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="1a613-124">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="1a613-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="1a613-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a613-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
