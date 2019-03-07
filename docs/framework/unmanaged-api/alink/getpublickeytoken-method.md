---
title: GetPublicKeyToken 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0481cfc3fa88aeb6fd7cd6ba93554d426f8eb2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492051"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="dd505-102">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="dd505-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="dd505-103">지정 된 키 파일 또는 키 컨테이너에 대 한 공개 키 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd505-104">구문</span><span class="sxs-lookup"><span data-stu-id="dd505-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd505-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd505-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="dd505-106">키의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="dd505-107">키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="dd505-108">저장할 키 토큰 인 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="dd505-109">표시 되는 버퍼를 바이트 단위로 크기를 지정 `pvPublicKeyToken`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="dd505-110">반환 시 실제 사용 된 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd505-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="dd505-111">Return Value</span></span>  
 <span data-ttu-id="dd505-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd505-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd505-113">Requirements</span></span>  
 <span data-ttu-id="dd505-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd505-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd505-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd505-115">See also</span></span>
- [<span data-ttu-id="dd505-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd505-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="dd505-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd505-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="dd505-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="dd505-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
