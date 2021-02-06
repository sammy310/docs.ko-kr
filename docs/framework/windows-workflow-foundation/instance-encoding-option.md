---
description: '자세히 알아보기: 인스턴스 인코딩 옵션'
title: 인스턴스 인코딩 옵션
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: 8cca7fd536673ca99b1014173e172508e3d97b7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631166"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="6fe09-103">인스턴스 인코딩 옵션</span><span class="sxs-lookup"><span data-stu-id="6fe09-103">Instance Encoding Option</span></span>

<span data-ttu-id="6fe09-104">SQL 워크플로 인스턴스 저장소의 **인스턴스 인코딩 옵션** 속성을 사용 하면 sql 지 속성 공급자가 지 속성 데이터베이스에 정보를 저장 하기 전에 GZip 알고리즘을 사용 하 여 워크플로 인스턴스 상태 정보를 압축할지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-104">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="6fe09-105">이 속성에 허용되는 값은 GZip과 None입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-105">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="6fe09-106">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-106">The default value is None.</span></span> <span data-ttu-id="6fe09-107">다음 목록에서는 이러한 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-107">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="6fe09-108">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="6fe09-108">**GZip**.</span></span> <span data-ttu-id="6fe09-109">지속성 공급자가 지속성 데이터베이스에 상태 정보를 유지하기 전에 GZip 알고리즘을 사용하여 상태 정보를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-109">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="6fe09-110">**없음**.</span><span class="sxs-lookup"><span data-stu-id="6fe09-110">**None**.</span></span> <span data-ttu-id="6fe09-111">지속성 공급자가 지속성 데이터베이스에 정보를 저장하기 전에 상태 정보를 인코딩하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-111">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="6fe09-112">GZip을 사용하여 워크플로 인스턴스 상태 정보를 인코딩하면 SQL 데이터베이스에서 메모리 사용을 줄일 수 있으며 데이터베이스가 네트워크에서 워크플로 서비스 호스트를 실행하는 컴퓨터와 다른 컴퓨터에 상주할 경우 네트워크 사용도 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-112">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="6fe09-113">일반적인 지침은 워크플로 인스턴스 상태가 작은 경우 **인스턴스 인코딩 옵션** 속성을 **None** 으로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe09-113">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
