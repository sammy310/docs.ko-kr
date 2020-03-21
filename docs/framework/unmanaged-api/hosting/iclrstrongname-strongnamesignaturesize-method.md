---
title: ICLRStrongName::StrongNameSignatureSize 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: e789996af3aedd17251fc52cde52a336f65053ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176346"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="548ba-102">ICLRStrongName::StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="548ba-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="548ba-103">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="548ba-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="548ba-104">이 메서드는 일반적으로 지연 서명 된 어셈블리를 만들 때 파일에 예약할 공간을 결정 하기 위해 컴파일러에 의해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="548ba-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="548ba-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="548ba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="548ba-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="548ba-107">【인】 강력한 이름 서명을 생성하는 데 사용되는 키 쌍의 공용 부분을 포함하는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 형식의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="548ba-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="548ba-108">【인】 의 크기(바이트)입니다. `pbPublicKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="548ba-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="548ba-109">【인】 강력한 이름 서명을 저장하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="548ba-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="548ba-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="548ba-110">Return Value</span></span>  
 <span data-ttu-id="548ba-111">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="548ba-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548ba-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="548ba-112">Requirements</span></span>  
 <span data-ttu-id="548ba-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="548ba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548ba-114">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="548ba-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="548ba-115">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="548ba-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="548ba-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548ba-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="548ba-117">See also</span></span>

- [<span data-ttu-id="548ba-118">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="548ba-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
