---
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
ms.openlocfilehash: b1c005e58f18b03a7da5f3836f719b95c41bca95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684943"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="6a564-102">EmitManifest 메서드</span><span class="sxs-lookup"><span data-stu-id="6a564-102">EmitManifest Method</span></span>

<span data-ttu-id="6a564-103">최종 매니페스트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-103">Emits the final manifest.</span></span> <span data-ttu-id="6a564-104">다른 모든 파일을 가져온 후이 메서드를 호출 하 고 모든 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="6a564-105">바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6a564-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a564-106">구문</span><span class="sxs-lookup"><span data-stu-id="6a564-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a564-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a564-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6a564-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="6a564-109">[StrongNameSignatureSize 함수](../strong-naming/strongnamesignaturesize-function.md)에서 검색 된 어셈블리 파일에서 예약할 크기를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="6a564-110">선택적으로 어셈블리 매니페스트 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a564-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="6a564-111">Return Value</span></span>  

 <span data-ttu-id="6a564-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a564-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a564-113">Requirements</span></span>  

 <span data-ttu-id="6a564-114">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a564-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a564-115">참조</span><span class="sxs-lookup"><span data-stu-id="6a564-115">See also</span></span>

- [<span data-ttu-id="6a564-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a564-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6a564-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a564-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6a564-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="6a564-118">ALink API</span></span>](index.md)
