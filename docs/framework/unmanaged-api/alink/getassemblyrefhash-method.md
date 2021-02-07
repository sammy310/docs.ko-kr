---
description: '자세한 정보: GetAssemblyRefHash 메서드'
title: GetAssemblyRefHash 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
ms.openlocfilehash: d8222d2fdd2c05ca1a23f881989dc344ba294bc1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718475"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="15ea6-103">GetAssemblyRefHash 메서드</span><span class="sxs-lookup"><span data-stu-id="15ea6-103">GetAssemblyRefHash Method</span></span>

<span data-ttu-id="15ea6-104">지정 된 어셈블리에 대 한 해시 blob를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ea6-104">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ea6-105">구문</span><span class="sxs-lookup"><span data-stu-id="15ea6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ea6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15ea6-106">Parameters</span></span>  

 `FileToken`  
 <span data-ttu-id="15ea6-107">해시가 참조할 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15ea6-107">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="15ea6-108">결과 해시 blob을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="15ea6-108">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="15ea6-109">해시 blob의 크기 (바이트)를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ea6-109">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15ea6-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="15ea6-110">Return Value</span></span>  

 <span data-ttu-id="15ea6-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ea6-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ea6-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15ea6-112">Requirements</span></span>  

 <span data-ttu-id="15ea6-113">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="15ea6-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ea6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15ea6-114">See also</span></span>

- [<span data-ttu-id="15ea6-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ea6-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="15ea6-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ea6-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="15ea6-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="15ea6-117">ALink API</span></span>](index.md)
