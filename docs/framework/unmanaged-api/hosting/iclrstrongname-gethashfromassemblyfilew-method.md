---
description: '자세히 알아보기: ICLRStrongName:: GetHashFromAssemblyFileW 메서드'
title: ICLRStrongName::GetHashFromAssemblyFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 27123ed8217d49765fe3fd7c19efc92f4e770722
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637081"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="402f1-103">ICLRStrongName::GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="402f1-103">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="402f1-104">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-104">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="402f1-105">구문</span><span class="sxs-lookup"><span data-stu-id="402f1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="402f1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="402f1-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="402f1-107">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-107">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="402f1-108">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-108">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="402f1-109">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="402f1-110">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="402f1-111">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="402f1-112">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="402f1-113">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="402f1-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="402f1-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="402f1-114">Return Value</span></span>  

 <span data-ttu-id="402f1-115">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="402f1-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="402f1-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="402f1-116">Requirements</span></span>  

 <span data-ttu-id="402f1-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="402f1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="402f1-118">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="402f1-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="402f1-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="402f1-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="402f1-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="402f1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402f1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="402f1-121">See also</span></span>

- [<span data-ttu-id="402f1-122">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="402f1-122">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="402f1-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="402f1-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
