---
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
ms.openlocfilehash: e94bfe6151ed42886355423a838f21e13748ec61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685775"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="8acb7-102">ICLRStrongName::GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="8acb7-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="8acb7-103">유니코드 문자열로 지정된 파일 내용에 대해 해시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8acb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="8acb7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8acb7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8acb7-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="8acb7-106">진행 해시할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="8acb7-107">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8acb7-108">[in, out] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8acb7-109">기본 해시 알고리즘에 대해 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8acb7-110">제한이 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8acb7-111">진행 요청 된 최대 크기 `pbHash` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8acb7-112">제한이 반환 된 크기 (바이트)입니다 `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="8acb7-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8acb7-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="8acb7-113">Return Value</span></span>  

 <span data-ttu-id="8acb7-114">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="8acb7-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8acb7-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8acb7-115">Requirements</span></span>  

 <span data-ttu-id="8acb7-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8acb7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8acb7-117">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8acb7-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8acb7-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8acb7-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8acb7-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8acb7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acb7-120">참조</span><span class="sxs-lookup"><span data-stu-id="8acb7-120">See also</span></span>

- [<span data-ttu-id="8acb7-121">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="8acb7-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8acb7-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8acb7-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
