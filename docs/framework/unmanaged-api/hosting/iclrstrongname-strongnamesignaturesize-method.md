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
ms.openlocfilehash: 7f6865c3d6dffa3b551d4e5e0636b1e386be8baa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134980"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="8138d-102">ICLRStrongName::StrongNameSignatureSize 메서드</span><span class="sxs-lookup"><span data-stu-id="8138d-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="8138d-103">강력한 이름 서명의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="8138d-104">이 메서드는 일반적으로 컴파일러가 지연 서명 된 어셈블리를 만들 때 파일에서 예약할 공간의 크기를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8138d-105">구문</span><span class="sxs-lookup"><span data-stu-id="8138d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8138d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8138d-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="8138d-107">진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 형식의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="8138d-108">진행 `pbPublicKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="8138d-109">진행 강력한 이름 서명을 저장 하는 데 필요한 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8138d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="8138d-110">Return Value</span></span>  
 <span data-ttu-id="8138d-111">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).</span><span class="sxs-lookup"><span data-stu-id="8138d-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8138d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8138d-112">Requirements</span></span>  
 <span data-ttu-id="8138d-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8138d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8138d-114">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8138d-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8138d-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8138d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8138d-116">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8138d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8138d-117">참조</span><span class="sxs-lookup"><span data-stu-id="8138d-117">See also</span></span>

- [<span data-ttu-id="8138d-118">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8138d-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
