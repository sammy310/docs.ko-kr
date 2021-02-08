---
description: '자세히 알아보기: ICLRStrongName:: GetHashFromHandle 메서드'
title: ICLRStrongName::GetHashFromHandle 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: 30248b5cb5d102adaa06293c92cc4f21e905cba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799683"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="2d8dd-103">ICLRStrongName::GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="2d8dd-103">ICLRStrongName::GetHashFromHandle Method</span></span>

<span data-ttu-id="2d8dd-104">지정 된 해시 알고리즘을 사용 하 여 지정 된 파일 핸들이 있는 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-104">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d8dd-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d8dd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d8dd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d8dd-106">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="2d8dd-107">진행 해시할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-107">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="2d8dd-108">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="2d8dd-109">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="2d8dd-110">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="2d8dd-111">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="2d8dd-112">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="2d8dd-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d8dd-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="2d8dd-113">Return Value</span></span>  

 <span data-ttu-id="2d8dd-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="2d8dd-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d8dd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d8dd-115">Requirements</span></span>  

 <span data-ttu-id="2d8dd-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d8dd-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2d8dd-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2d8dd-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d8dd-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d8dd-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d8dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8dd-120">참조</span><span class="sxs-lookup"><span data-stu-id="2d8dd-120">See also</span></span>

- [<span data-ttu-id="2d8dd-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d8dd-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
