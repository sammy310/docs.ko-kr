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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179409"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="511d0-102">ExportNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="511d0-102">ExportNestedType Method</span></span>
<span data-ttu-id="511d0-103">중첩된 형식을 내보낼 수 있는 것으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="511d0-104">[ExportType 메서드는](exporttype-method.md) 중첩된 형식을 내보낼 수도 있지만 이 방법은 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="511d0-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="511d0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="511d0-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="511d0-107">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="511d0-108">내보낼 수 있도록 할 형식을 정의하는 파일 토큰 또는 파일 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="511d0-109">내보낼 수 있도록 할 형식의 토큰을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="511d0-110">상위 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="511d0-111">내보낼 정규화된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="511d0-112">`ComType`또는 와 `tdPublic` `tdNested`같은 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="511d0-113">이 값은 [정의ExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="511d0-114">내보낸 형식에 대한 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="511d0-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="511d0-115">Return Value</span></span>  
 <span data-ttu-id="511d0-116">메서드가 성공하면 S_OK 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="511d0-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="511d0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="511d0-117">Requirements</span></span>  
 <span data-ttu-id="511d0-118">alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="511d0-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511d0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="511d0-119">See also</span></span>

- [<span data-ttu-id="511d0-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="511d0-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="511d0-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="511d0-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="511d0-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="511d0-122">ALink API</span></span>](index.md)
