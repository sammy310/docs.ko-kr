---
title: 인스턴스 인코딩 옵션
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773846"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="341d3-102">인스턴스 인코딩 옵션</span><span class="sxs-lookup"><span data-stu-id="341d3-102">Instance Encoding Option</span></span>
<span data-ttu-id="341d3-103">합니다 **Instance Encoding Option** SQL 워크플로 인스턴스 저장소의 속성을 사용 하면 SQL 지 속성 공급자를 저장 하기 전에 GZip 알고리즘을 사용 하 여 워크플로 인스턴스 상태 정보를 압축 해야 하는지 여부를 지정할 수는 지 속성 데이터베이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="341d3-104">이 속성에 대 한 허용 되는 값은 다음과 같습니다. GZip 및 None입니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="341d3-105">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-105">The default value is None.</span></span> <span data-ttu-id="341d3-106">다음 목록에서는 이러한 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="341d3-107">**GZip**합니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-107">**GZip**.</span></span> <span data-ttu-id="341d3-108">지속성 공급자가 지속성 데이터베이스에 상태 정보를 유지하기 전에 GZip 알고리즘을 사용하여 상태 정보를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="341d3-109">**없음**.</span><span class="sxs-lookup"><span data-stu-id="341d3-109">**None**.</span></span> <span data-ttu-id="341d3-110">지속성 공급자가 지속성 데이터베이스에 정보를 저장하기 전에 상태 정보를 인코딩하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="341d3-111">GZip을 사용하여 워크플로 인스턴스 상태 정보를 인코딩하면 SQL 데이터베이스에서 메모리 사용을 줄일 수 있으며 데이터베이스가 네트워크에서 워크플로 서비스 호스트를 실행하는 컴퓨터와 다른 컴퓨터에 상주할 경우 네트워크 사용도 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341d3-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="341d3-112">일반 지침을 설정 하는 것은 **Instance Encoding Option** 속성을 **None** 워크플로 인스턴스 상태가 작은 경우.</span><span class="sxs-lookup"><span data-stu-id="341d3-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
