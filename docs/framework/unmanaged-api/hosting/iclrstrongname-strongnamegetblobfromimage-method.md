---
title: ICLRStrongName::StrongNameGetBlobFromImage 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: a0bcc62a1715fb455f0affee64a351cabe0ba3f6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901129"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="29aab-102">ICLRStrongName::StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="29aab-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="29aab-103">지정된 메모리 주소에 있는 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29aab-104">구문</span><span class="sxs-lookup"><span data-stu-id="29aab-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29aab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29aab-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="29aab-106">진행 매핑된 어셈블리 매니페스트의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="29aab-107">진행 `pbBase`에 있는 이미지의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="29aab-108">진행 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="29aab-109">[in, out] `pbBlob`요청 된 최대 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="29aab-110">반환 시 `pbBlob`의 실제 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29aab-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="29aab-111">Return Value</span></span>  
 <span data-ttu-id="29aab-112">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="29aab-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29aab-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29aab-113">Requirements</span></span>  
 <span data-ttu-id="29aab-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29aab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29aab-115">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="29aab-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="29aab-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29aab-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29aab-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29aab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29aab-118">참조</span><span class="sxs-lookup"><span data-stu-id="29aab-118">See also</span></span>

- [<span data-ttu-id="29aab-119">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="29aab-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="29aab-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29aab-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
