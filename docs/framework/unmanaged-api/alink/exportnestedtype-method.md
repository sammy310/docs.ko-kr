---
title: ExportNestedType 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789963"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="d79ce-102">ExportNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="d79ce-102">ExportNestedType Method</span></span>
<span data-ttu-id="d79ce-103">내보낼 수 있도록 중첩 된 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="d79ce-104">합니다 [ExportType 메서드](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) 내보내기 중첩 형식 수도 있지만이 메서드는 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79ce-105">구문</span><span class="sxs-lookup"><span data-stu-id="d79ce-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="d79ce-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d79ce-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d79ce-107">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d79ce-108">파일 토큰 또는 내보낼 수 있도록 지정할 형식을 정의 하는 파일의 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d79ce-109">내보낼 수 있도록 지정할 형식의 토큰을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="d79ce-110">부모 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d79ce-111">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d79ce-112">`ComType` 와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="d79ce-113">이 값을 전달할 수 있습니다 [DefineExportedType 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="d79ce-114">내보낸된 형식에 대 한 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79ce-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="d79ce-115">Return Value</span></span>  
 <span data-ttu-id="d79ce-116">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79ce-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79ce-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d79ce-117">Requirements</span></span>  
 <span data-ttu-id="d79ce-118">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="d79ce-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79ce-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d79ce-119">See also</span></span>

- [<span data-ttu-id="d79ce-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d79ce-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d79ce-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d79ce-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d79ce-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="d79ce-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
