---
description: '자세히 알아보기: ICLRStrongName:: GetHashFromAssemblyFile 메서드'
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
ms.openlocfilehash: 40a8e2aabe9ade00243c535d63389f4265cc6ab0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799703"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="cb36f-103">ICLRStrongName::GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="cb36f-103">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>

<span data-ttu-id="cb36f-104">지정된 해시 알고리즘을 사용하여 지정된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-104">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb36f-105">구문</span><span class="sxs-lookup"><span data-stu-id="cb36f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb36f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb36f-106">Parameters</span></span>  

 `szFilePath`  
 <span data-ttu-id="cb36f-107">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-107">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cb36f-108">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cb36f-109">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cb36f-110">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cb36f-111">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cb36f-112">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="cb36f-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb36f-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="cb36f-113">Return Value</span></span>  

 <span data-ttu-id="cb36f-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="cb36f-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb36f-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb36f-115">Requirements</span></span>  

 <span data-ttu-id="cb36f-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb36f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb36f-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="cb36f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cb36f-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb36f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb36f-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb36f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb36f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb36f-120">See also</span></span>

- [<span data-ttu-id="cb36f-121">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="cb36f-121">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="cb36f-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb36f-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
