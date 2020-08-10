---
title: '샘플 XML 파일: 네임스페이스의 숫자 데이터3'
description: 이 XML 파일은 LINQ to XML 설명서의 다양한 예제에서 사용됩니다. 여기에는 합계, 평균 및 그룹화에 대한 데이터가 포함됩니다. XML은 네임스페이스에 있습니다.
ms.date: 07/20/2015
ms.assetid: 51750cab-3c66-4511-90fb-b9d211308d31
ms.openlocfilehash: fe467604840851c2af2533a620f9b7e32367fbb3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302505"
---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="b8553-105">샘플 XML 파일: 네임스페이스의 숫자 데이터</span><span class="sxs-lookup"><span data-stu-id="b8553-105">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="b8553-106">다음 XML 파일은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8553-106">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="b8553-107">이 파일에는 합계 및 평균을 구하고 그룹화할 숫자 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8553-107">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="b8553-108">XML은 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8553-108">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="b8553-109">데이터</span><span class="sxs-lookup"><span data-stu-id="b8553-109">Data</span></span>  
  
```xml  
<Root xmlns='http://www.adatum.com'>  
  <TaxRate>7.25</TaxRate>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>24.50</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>1</Quantity>  
    <Price>89.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>5</Quantity>  
    <Price>4.95</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>66.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>10</Quantity>  
    <Price>.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>15</Quantity>  
    <Price>29.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>8</Quantity>  
    <Price>6.99</Price>  
  </Data>  
</Root>  
```  
