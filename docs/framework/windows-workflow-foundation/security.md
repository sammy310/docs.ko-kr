---
title: 보안
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: e4419a7a73015541e0a75b4f8c615485c5fdac1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267275"
---
# <a name="security"></a><span data-ttu-id="e489f-102">보안</span><span class="sxs-lookup"><span data-stu-id="e489f-102">Security</span></span>

<span data-ttu-id="e489f-103">SQL 워크플로 인스턴스 저장소에서는 다음과 같은 데이터베이스 보안 역할을 사용하여 지속성 데이터베이스의 인스턴스 상태 정보에 대한 액세스에 보안을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
- <span data-ttu-id="e489f-104">**DurableInstancing. 예: system.activities.durableinstancing.instancestoreusers**.</span><span class="sxs-lookup"><span data-stu-id="e489f-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="e489f-105">이 역할에는 공용 뷰에 대한 읽기 및 쓰기 액세스 권한과 인스턴스 생성, 로드 및 저장과 관련된 저장 프로시저에 대한 실행 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
- <span data-ttu-id="e489f-106">**DurableInstancing. InstanceStoreObservers**.</span><span class="sxs-lookup"><span data-stu-id="e489f-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="e489f-107">이 역할에는 공용 뷰에 대한 읽기 전용 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-107">This role has read-only access to public views.</span></span>  
  
- <span data-ttu-id="e489f-108">**DurableInstancing. WorkflowActivationUsers**.</span><span class="sxs-lookup"><span data-stu-id="e489f-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="e489f-109">이 역할은 인스턴스 활성화 프로세스에 포함되는 저장 프로시저에 대한 실행 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="e489f-110">인스턴스 활성화에 대 한 자세한 내용은 [인스턴스 활성화](instance-activation.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e489f-110">For more information about instance activation, see [Instance Activation](instance-activation.md).</span></span> <span data-ttu-id="e489f-111">일반 호스트 (Windows Server AppFabric의 호스팅 기능에 대 한 워크플로 관리 서비스)가 실행 되는 사용자 계정은이 데이터베이스 역할에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-111">The user account under which a generic host (such as the Workflow Management Service of the hosting features of Windows Server AppFabric) runs should be added to this database role.</span></span>  
  
 <span data-ttu-id="e489f-112">Windows Server 응용 프로그램 패브릭을 사용 하는 지 속성 저장소의 보안에 대 한 자세한 내용은 [App fabric의 지 속성 저장소에 대 한 보안 구성](/previous-versions/appfabric/ff431727(v=azure.10)) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e489f-112">For more information about security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](/previous-versions/appfabric/ff431727(v=azure.10))</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e489f-113">인스턴스 저장소에 있는 고유 인스턴스 데이터에 대한 액세스 권한을 가진 클라이언트는 동일한 인스턴스 저장소에 있는 모든 다른 인스턴스에 대한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="e489f-114">인스턴스 저장소는 인스턴스 수준의 보안 권한 지정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="e489f-115">다른 저장소에 대한 액세스 권한을 갖도록 하려면 별도의 인스턴스 저장소를 만들고 다른 그룹/사용자를 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e489f-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
