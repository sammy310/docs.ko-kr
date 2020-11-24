---
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
ms.openlocfilehash: 68bfdb2f66147b54c75b8f577a01278016e248b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685736"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="8771b-102">ICLRStrongName::GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="8771b-102">ICLRStrongName::GetHashFromHandle Method</span></span>

<span data-ttu-id="8771b-103">지정 된 해시 알고리즘을 사용 하 여 지정 된 파일 핸들이 있는 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8771b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8771b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8771b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8771b-105">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="8771b-106">진행 해시할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8771b-107">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8771b-108">기본 알고리즘에는 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8771b-109">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8771b-110">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8771b-111">제한이 반환 된의 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="8771b-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8771b-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="8771b-112">Return Value</span></span>  

 <span data-ttu-id="8771b-113">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="8771b-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8771b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8771b-114">Requirements</span></span>  

 <span data-ttu-id="8771b-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8771b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8771b-116">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8771b-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8771b-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8771b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8771b-118">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8771b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8771b-119">참조</span><span class="sxs-lookup"><span data-stu-id="8771b-119">See also</span></span>

- [<span data-ttu-id="8771b-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8771b-120">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
