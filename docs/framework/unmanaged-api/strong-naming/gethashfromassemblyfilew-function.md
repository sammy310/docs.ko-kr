---
title: GetHashFromAssemblyFileW 함수
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a88adec508d80a40ec044e5011d3115e197e334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000547"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="672b3-102">GetHashFromAssemblyFileW 함수</span><span class="sxs-lookup"><span data-stu-id="672b3-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="672b3-103">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="672b3-104">어셈블리 파일의 경로를 유니코드 문자열로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="672b3-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-105">This function has been deprecated.</span></span> <span data-ttu-id="672b3-106">사용 된 [iclrstrongname:: Gethashfromassemblyfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672b3-107">구문</span><span class="sxs-lookup"><span data-stu-id="672b3-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="672b3-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="672b3-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="672b3-109">[in] 해시할 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="672b3-110">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="672b3-111">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="672b3-112">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="672b3-113">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="672b3-114">[in] 요청 된 최대 크기인 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="672b3-115">[out] 크기 (바이트)를 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="672b3-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="672b3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="672b3-116">Requirements</span></span>  
 <span data-ttu-id="672b3-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="672b3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="672b3-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="672b3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="672b3-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="672b3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="672b3-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="672b3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672b3-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="672b3-121">See also</span></span>

- [<span data-ttu-id="672b3-122">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="672b3-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="672b3-123">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="672b3-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="672b3-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="672b3-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
