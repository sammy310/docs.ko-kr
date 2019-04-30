---
title: SetPEKind 메서드
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dec04fa267c61798a3340e9d1e18150b812e9eaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949008"
---
# <a name="setpekind-method"></a><span data-ttu-id="fdd7c-102">SetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="fdd7c-102">SetPEKind Method</span></span>
<span data-ttu-id="fdd7c-103">이식 가능한 실행 파일 형식에 시스템별 또는 알 수 없는 컴퓨터를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdd7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdd7c-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="fdd7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdd7c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fdd7c-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fdd7c-107">PE 형식 설정 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="fdd7c-108">NULL 일 수 `AssemblyID` 는 바인딩되지 않은 netmodule를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="fdd7c-109">PE에 표시 된 대로 유형의 합니다 [CorPEKind 열거형](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="fdd7c-110">대상 컴퓨터 아키텍처, NT 헤더에 표시 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdd7c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="fdd7c-111">Return Value</span></span>  
 <span data-ttu-id="fdd7c-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdd7c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdd7c-113">Requirements</span></span>  
 <span data-ttu-id="fdd7c-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fdd7c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdd7c-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fdd7c-115">See also</span></span>

- [<span data-ttu-id="fdd7c-116">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="fdd7c-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="fdd7c-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd7c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fdd7c-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdd7c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fdd7c-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="fdd7c-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
