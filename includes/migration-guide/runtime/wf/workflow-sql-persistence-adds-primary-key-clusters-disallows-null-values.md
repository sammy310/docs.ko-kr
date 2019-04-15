---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236239"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="c4201-101">워크플로 SQL 지속성은 기본 키 클러스터를 추가하고 일부 열에서 null 값을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c4201-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c4201-102">Details</span></span>|<span data-ttu-id="c4201-103">.NET Framework 4.7부터 SqlWorkflowInstanceStoreSchema.sql 스크립트로 SQL 워크플로 인스턴스 저장소(SWIS)용으로 만든 테이블은 클러스터된 기본 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="c4201-104">이로 인해 ID는 <code>null</code> 값을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="c4201-105">SWIS 작업은 이 변경의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="c4201-106">SQL Server 트랜잭션 복제를 지원하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="c4201-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c4201-107">Suggestion</span></span>|<span data-ttu-id="c4201-108">이 변경 내용을 적용하려면 SQL 파일 SqlWorkflowInstanceStoreSchemaUpgrade.sql을 기존 설치에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4201-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="c4201-109">새 데이터베이스 설치는 자동으로 변경됩니다. </span><span class="sxs-lookup"><span data-stu-id="c4201-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="c4201-110">범위</span><span class="sxs-lookup"><span data-stu-id="c4201-110">Scope</span></span>|<span data-ttu-id="c4201-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c4201-111">Edge</span></span>|
|<span data-ttu-id="c4201-112">버전</span><span class="sxs-lookup"><span data-stu-id="c4201-112">Version</span></span>|<span data-ttu-id="c4201-113">4.7</span><span class="sxs-lookup"><span data-stu-id="c4201-113">4.7</span></span>|
|<span data-ttu-id="c4201-114">형식</span><span class="sxs-lookup"><span data-stu-id="c4201-114">Type</span></span>|<span data-ttu-id="c4201-115">런타임</span><span class="sxs-lookup"><span data-stu-id="c4201-115">Runtime</span></span>|
