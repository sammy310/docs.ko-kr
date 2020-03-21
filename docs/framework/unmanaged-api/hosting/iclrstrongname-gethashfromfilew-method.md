---
title: ICLRStrongName::GetHashFromFileW 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176372"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="a3bcb-102">ICLRStrongName::GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="a3bcb-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="a3bcb-103">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3bcb-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3bcb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a3bcb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3bcb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a3bcb-106">【인】 해시할 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a3bcb-107">【인, 아웃】 해시를 생성할 때 사용할 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="a3bcb-108">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의된 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="a3bcb-109">0으로 설정된 경우 `piHashAlg` 기본 알고리즘 CALG_SHA-1이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a3bcb-110">【아웃】 생성된 해시를 포함하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a3bcb-111">【인】 을 가리키는 버퍼의 최대 `pbHash`크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a3bcb-112">【아웃】 의 크기(바이트)입니다. `pbHash`</span><span class="sxs-lookup"><span data-stu-id="a3bcb-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3bcb-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="a3bcb-113">Return Value</span></span>  
 <span data-ttu-id="a3bcb-114">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="a3bcb-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3bcb-115">설명</span><span class="sxs-lookup"><span data-stu-id="a3bcb-115">Remarks</span></span>  
 <span data-ttu-id="a3bcb-116">이 메서드는 [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) 메서드와 동일 하지만 파일 이름 사양ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3bcb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3bcb-117">Requirements</span></span>  
 <span data-ttu-id="a3bcb-118">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3bcb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3bcb-119">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="a3bcb-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3bcb-120">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a3bcb-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3bcb-121">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3bcb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3bcb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3bcb-122">See also</span></span>

- [<span data-ttu-id="a3bcb-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="a3bcb-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="a3bcb-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a3bcb-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
