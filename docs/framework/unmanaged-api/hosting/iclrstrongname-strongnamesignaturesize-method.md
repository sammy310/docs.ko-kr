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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8bf6d69f8490f05532df3e164107760c2b574e2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755013"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="c438e-102">ICLRStrongName::StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c438e-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="c438e-103">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c438e-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="c438e-104">이 메서드는 일반적으로 기본 서명이 연기 된 어셈블리를 만들 때 파일에 예약할 공간 결정 되는 컴파일러에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c438e-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c438e-105">구문</span><span class="sxs-lookup"><span data-stu-id="c438e-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c438e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c438e-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c438e-107">[in] 형식의 구조체 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c438e-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c438e-108">[in] 크기 (바이트)의 `pbPublicKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="c438e-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="c438e-109">[in] 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c438e-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c438e-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c438e-110">Return Value</span></span>  
 <span data-ttu-id="c438e-111">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="c438e-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c438e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c438e-112">Requirements</span></span>  
 <span data-ttu-id="c438e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c438e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c438e-114">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c438e-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c438e-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c438e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c438e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c438e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c438e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="c438e-117">See also</span></span>

- [<span data-ttu-id="c438e-118">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c438e-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
