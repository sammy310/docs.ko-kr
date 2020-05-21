---
title: ICLRStrongName::GetHashFromAssemblyFile 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 007de0365bf70b1f4a9a9e0f01807e7fdac19f54
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762151"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="2c57a-102">ICLRStrongName::GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="2c57a-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="2c57a-103">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c57a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c57a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c57a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c57a-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="2c57a-106">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2c57a-107">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2c57a-108">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2c57a-109">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2c57a-110">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2c57a-111">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2c57a-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c57a-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="2c57a-112">Return Value</span></span>  
 <span data-ttu-id="2c57a-113">`S_OK`메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="2c57a-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c57a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c57a-114">Requirements</span></span>  
 <span data-ttu-id="2c57a-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c57a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c57a-116">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2c57a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2c57a-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c57a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c57a-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c57a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c57a-119">참조</span><span class="sxs-lookup"><span data-stu-id="2c57a-119">See also</span></span>

- [<span data-ttu-id="2c57a-120">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="2c57a-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="2c57a-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c57a-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
