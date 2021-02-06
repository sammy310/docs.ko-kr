---
description: '자세히 알아보기: EmitManifest 메서드'
title: EmitManifest 메서드
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: 770631864c030c067feb0b02d2f00c36076aa44c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638277"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="8621b-103">EmitManifest 메서드</span><span class="sxs-lookup"><span data-stu-id="8621b-103">EmitManifest Method</span></span>

<span data-ttu-id="8621b-104">최종 매니페스트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-104">Emits the final manifest.</span></span> <span data-ttu-id="8621b-105">다른 모든 파일을 가져온 후이 메서드를 호출 하 고 모든 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-105">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="8621b-106">바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8621b-106">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8621b-107">구문</span><span class="sxs-lookup"><span data-stu-id="8621b-107">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8621b-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8621b-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="8621b-109">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-109">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="8621b-110">[StrongNameSignatureSize 함수](../strong-naming/strongnamesignaturesize-function.md)에서 검색 된 어셈블리 파일에서 예약할 크기를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-110">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="8621b-111">선택적으로 어셈블리 매니페스트 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-111">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8621b-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="8621b-112">Return Value</span></span>  

 <span data-ttu-id="8621b-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8621b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8621b-114">Requirements</span></span>  

 <span data-ttu-id="8621b-115">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8621b-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8621b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8621b-116">See also</span></span>

- [<span data-ttu-id="8621b-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8621b-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8621b-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8621b-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8621b-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="8621b-119">ALink API</span></span>](index.md)
