---
title: GetHashFromHandle 함수
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48dd987896536006fe81bc01528cadb507123e27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049429"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="7f7b5-102">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="7f7b5-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="7f7b5-103">지정된 해시 알고리즘을 사용하여 지정된 파일 핸들로 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7f7b5-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-104">This function has been deprecated.</span></span> <span data-ttu-id="7f7b5-105">사용 된 [iclrstrongname:: Gethashfromhandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f7b5-106">구문</span><span class="sxs-lookup"><span data-stu-id="7f7b5-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f7b5-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f7b5-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="7f7b5-108">[in] 해시 될 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="7f7b5-109">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="7f7b5-110">기본 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="7f7b5-111">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="7f7b5-112">[in] 요청 된 최대 크기인 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="7f7b5-113">[out] 반환 된 바이트의 크기, `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f7b5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f7b5-114">Requirements</span></span>  
 <span data-ttu-id="7f7b5-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f7b5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f7b5-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7f7b5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7f7b5-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7f7b5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f7b5-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f7b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f7b5-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f7b5-119">See also</span></span>

- [<span data-ttu-id="7f7b5-120">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="7f7b5-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="7f7b5-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f7b5-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
