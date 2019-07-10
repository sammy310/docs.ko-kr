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
ms.openlocfilehash: ec2c357cd56670f4f2deed8023bed7842a7f4ed7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741878"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="5c35e-102">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="5c35e-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="5c35e-103">지정 된 키 파일 또는 키 컨테이너에 대 한 공개 키 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c35e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c35e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c35e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c35e-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="5c35e-106">키의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="5c35e-107">키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="5c35e-108">저장할 키 토큰 인 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="5c35e-109">표시 되는 버퍼를 바이트 단위로 크기를 지정 `pvPublicKeyToken`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="5c35e-110">반환 시 실제 사용 된 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c35e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="5c35e-111">Return Value</span></span>  
 <span data-ttu-id="5c35e-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c35e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c35e-113">Requirements</span></span>  
 <span data-ttu-id="5c35e-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c35e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c35e-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c35e-115">See also</span></span>

- [<span data-ttu-id="5c35e-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c35e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5c35e-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c35e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5c35e-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="5c35e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
