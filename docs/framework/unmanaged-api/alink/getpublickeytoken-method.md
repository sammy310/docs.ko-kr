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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447236"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="716fd-102">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="716fd-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="716fd-103">지정 된 keyfile 또는 키 컨테이너에 대 한 공개 키 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="716fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="716fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="716fd-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="716fd-106">키의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="716fd-107">키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="716fd-108">키 토큰을 저장할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="716fd-109">`pvPublicKeyToken`로 표시 되는 버퍼의 크기 (바이트)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="716fd-110">반환 시 실제 사용 된 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="716fd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="716fd-111">Return Value</span></span>  
 <span data-ttu-id="716fd-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716fd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="716fd-113">Requirements</span></span>  
 <span data-ttu-id="716fd-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="716fd-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716fd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="716fd-115">See also</span></span>

- [<span data-ttu-id="716fd-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="716fd-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="716fd-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="716fd-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="716fd-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="716fd-118">ALink API</span></span>](index.md)
