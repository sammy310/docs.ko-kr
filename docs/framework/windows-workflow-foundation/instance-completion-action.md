---
description: '자세히 알아보기: 인스턴스 완료 동작'
title: 인스턴스 완료 동작
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 84405ca9869369e4fe00b0049d628671a79a9f68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792689"
---
# <a name="instance-completion-action"></a><span data-ttu-id="ff325-103">인스턴스 완료 동작</span><span class="sxs-lookup"><span data-stu-id="ff325-103">Instance Completion Action</span></span>

<span data-ttu-id="ff325-104">SQL 워크플로 인스턴스 저장소의 **인스턴스 완료 동작** 속성을 사용 하면 인스턴스가 완료 된 후 워크플로 인스턴스의 데이터와 메타 데이터가 지 속성 데이터베이스에서 삭제 되는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-104">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="ff325-105">이 속성에 허용 되는 값은 **DeleteAll** 및 **DeleteNothing** 입니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-105">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="ff325-106">다음 목록에서는 이러한 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-106">The following list describes these options:</span></span>

- <span data-ttu-id="ff325-107">**DeleteAll(기본값).**</span><span class="sxs-lookup"><span data-stu-id="ff325-107">**DeleteAll (default).**</span></span> <span data-ttu-id="ff325-108">속성의 값을 DeleteAll로 설정하면 인스턴스가 완료된 후 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-108">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>

- <span data-ttu-id="ff325-109">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="ff325-109">**DeleteNothing.**</span></span> <span data-ttu-id="ff325-110">속성의 값을 DeleteNothing으로 설정하면 인스턴스가 완료된 후에도 워크플로 인스턴스의 데이터와 메타데이터가 지속성 데이터베이스에 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-110">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="ff325-111">인스턴스가 완료된 후 인스턴스 상태 정보를 유지하면 지속성 데이터베이스의 크기가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-111">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="ff325-112">데이터베이스 크기가 증가할수록 지속성 하위 시스템이 수행하는 데이터베이스 작업이 더 오래 걸리므로, 서비스가 성능 필요에 맞는 수준으로 수행되도록 하려면 정기적으로 지속성 데이터베이스에서 인스턴스 상태 정보를 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff325-112">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
