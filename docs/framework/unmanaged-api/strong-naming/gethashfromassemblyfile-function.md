---
title: GetHashFromAssemblyFile 함수
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 026115adc01e7dcdac3012255f0378cff6348f89
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780697"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="8cbef-102">GetHashFromAssemblyFile 함수</span><span class="sxs-lookup"><span data-stu-id="8cbef-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="8cbef-103">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="8cbef-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-104">This function has been deprecated.</span></span> <span data-ttu-id="8cbef-105">사용 된 [iclrstrongname:: Gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cbef-106">구문</span><span class="sxs-lookup"><span data-stu-id="8cbef-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cbef-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cbef-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="8cbef-108">[in] 해시할 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8cbef-109">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8cbef-110">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8cbef-111">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8cbef-112">[in] 요청 된 최대 크기인 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8cbef-113">[out] 크기 (바이트)를 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbef-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cbef-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cbef-114">Requirements</span></span>  
 <span data-ttu-id="8cbef-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8cbef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cbef-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8cbef-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8cbef-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8cbef-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8cbef-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cbef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbef-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="8cbef-119">See also</span></span>

- [<span data-ttu-id="8cbef-120">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="8cbef-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8cbef-121">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="8cbef-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="8cbef-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8cbef-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
