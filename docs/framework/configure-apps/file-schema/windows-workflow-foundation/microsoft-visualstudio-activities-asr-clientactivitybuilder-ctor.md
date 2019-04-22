---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133538"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="c165d-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="c165d-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="c165d-103">인스턴스를 만듭니다는 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c165d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c165d-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c165d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c165d-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="c165d-106">매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="c165d-106">Parameter Values</span></span>  
 <span data-ttu-id="c165d-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="c165d-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="c165d-108">: 작업 이름, 반환 형식 및 매개 변수 정보를 비롯하여 생성되는 워크플로 활동에서 수행될 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="c165d-109">이 매개 변수의 값이 아니어야 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="c165d-110">메시지 계약을 사용하고 한 메시지에 인수를 사용하는 동기 작업을 설명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="c165d-111">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="c165d-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="c165d-112">*configurationName*</span></span>  
  
 <span data-ttu-id="c165d-113">: 엔드포인트 구성 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="c165d-114">이 매개 변수의 안 **null** 이거나 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="c165d-115">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="c165d-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="c165d-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="c165d-117">: 작업의 서비스 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="c165d-118">이 매개 변수의 안 **null** 이거나 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="c165d-119">이러한 조건이 충족되지 않으면 생성자 및 이 클래스의 기타 메서드를 사용한 런타임 결과는 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c165d-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c165d-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="c165d-120">See also</span></span>

- [<span data-ttu-id="c165d-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="c165d-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
