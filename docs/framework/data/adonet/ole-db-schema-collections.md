---
description: OLE DB 스키마 컬렉션에 대해 자세히 알아보세요.
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: d4d4bae5387575bdaeaf013ed690e95aa3259068
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672623"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="1d5ee-103">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="1d5ee-103">OLE DB Schema Collections</span></span>

<span data-ttu-id="1d5ee-104">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5ee-104">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="1d5ee-105">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="1d5ee-105">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="1d5ee-106">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d5ee-106">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="1d5ee-107">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-107">Tables</span></span>  
  
- <span data-ttu-id="1d5ee-108">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-108">Columns</span></span>  
  
- <span data-ttu-id="1d5ee-109">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-109">Procedures</span></span>  
  
- <span data-ttu-id="1d5ee-110">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1d5ee-110">ProcedureParameters</span></span>  
  
- <span data-ttu-id="1d5ee-111">카탈로그</span><span class="sxs-lookup"><span data-stu-id="1d5ee-111">Catalog</span></span>  
  
- <span data-ttu-id="1d5ee-112">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-112">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1d5ee-113">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-113">Tables</span></span>  
  
|<span data-ttu-id="1d5ee-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-114">ColumnName</span></span>|<span data-ttu-id="1d5ee-115">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-116">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-117">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-117">String</span></span>|  
|<span data-ttu-id="1d5ee-118">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-118">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-119">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-119">String</span></span>|  
|<span data-ttu-id="1d5ee-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-120">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-121">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-121">String</span></span>|  
|<span data-ttu-id="1d5ee-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-122">TABLE_TYPE</span></span>|<span data-ttu-id="1d5ee-123">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-123">String</span></span>|  
|<span data-ttu-id="1d5ee-124">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-124">TABLE_GUID</span></span>|<span data-ttu-id="1d5ee-125">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-125">Guid</span></span>|  
|<span data-ttu-id="1d5ee-126">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-126">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-127">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-127">String</span></span>|  
|<span data-ttu-id="1d5ee-128">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-128">TABLE_PROPID</span></span>|<span data-ttu-id="1d5ee-129">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-129">Int64</span></span>|  
|<span data-ttu-id="1d5ee-130">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-130">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-131">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-132">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-132">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-133">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-133">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1d5ee-134">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-134">Columns</span></span>  
  
|<span data-ttu-id="1d5ee-135">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-135">ColumnName</span></span>|<span data-ttu-id="1d5ee-136">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-136">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-137">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-137">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-138">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-138">String</span></span>|  
|<span data-ttu-id="1d5ee-139">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-139">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-140">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-140">String</span></span>|  
|<span data-ttu-id="1d5ee-141">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-141">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-142">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-142">String</span></span>|  
|<span data-ttu-id="1d5ee-143">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-143">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-144">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-144">String</span></span>|  
|<span data-ttu-id="1d5ee-145">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-145">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-146">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-146">Guid</span></span>|  
|<span data-ttu-id="1d5ee-147">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-147">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-148">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-148">Int64</span></span>|  
|<span data-ttu-id="1d5ee-149">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-149">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-150">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-150">Int64</span></span>|  
|<span data-ttu-id="1d5ee-151">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-151">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1d5ee-152">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-152">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-153">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-153">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1d5ee-154">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-154">String</span></span>|  
|<span data-ttu-id="1d5ee-155">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-155">COLUMN_FLAGS</span></span>|<span data-ttu-id="1d5ee-156">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-156">Int64</span></span>|  
|<span data-ttu-id="1d5ee-157">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-157">IS_NULLABLE</span></span>|<span data-ttu-id="1d5ee-158">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-158">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-159">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-159">DATA_TYPE</span></span>|<span data-ttu-id="1d5ee-160">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-160">Int32</span></span>|  
|<span data-ttu-id="1d5ee-161">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-161">TYPE_GUID</span></span>|<span data-ttu-id="1d5ee-162">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-162">Guid</span></span>|  
|<span data-ttu-id="1d5ee-163">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-163">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1d5ee-164">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-164">Int64</span></span>|  
|<span data-ttu-id="1d5ee-165">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-165">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1d5ee-166">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-166">Int64</span></span>|  
|<span data-ttu-id="1d5ee-167">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-167">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1d5ee-168">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-168">Int32</span></span>|  
|<span data-ttu-id="1d5ee-169">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-169">NUMERIC_SCALE</span></span>|<span data-ttu-id="1d5ee-170">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-170">Int16</span></span>|  
|<span data-ttu-id="1d5ee-171">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-171">DATETIME_PRECISION</span></span>|<span data-ttu-id="1d5ee-172">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-172">Int64</span></span>|  
|<span data-ttu-id="1d5ee-173">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-173">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1d5ee-174">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-174">String</span></span>|  
|<span data-ttu-id="1d5ee-175">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-175">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1d5ee-176">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-176">String</span></span>|  
|<span data-ttu-id="1d5ee-177">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-177">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1d5ee-178">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-178">String</span></span>|  
|<span data-ttu-id="1d5ee-179">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-179">COLLATION_CATALOG</span></span>|<span data-ttu-id="1d5ee-180">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-180">String</span></span>|  
|<span data-ttu-id="1d5ee-181">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-181">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1d5ee-182">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-182">String</span></span>|  
|<span data-ttu-id="1d5ee-183">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-183">COLLATION_NAME</span></span>|<span data-ttu-id="1d5ee-184">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-184">String</span></span>|  
|<span data-ttu-id="1d5ee-185">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-185">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1d5ee-186">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-186">String</span></span>|  
|<span data-ttu-id="1d5ee-187">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-187">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1d5ee-188">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-188">String</span></span>|  
|<span data-ttu-id="1d5ee-189">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-189">DOMAIN_NAME</span></span>|<span data-ttu-id="1d5ee-190">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-190">String</span></span>|  
|<span data-ttu-id="1d5ee-191">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-191">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-192">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-192">String</span></span>|  
|<span data-ttu-id="1d5ee-193">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-193">COLUMN_LCID</span></span>|<span data-ttu-id="1d5ee-194">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-194">Int32</span></span>|  
|<span data-ttu-id="1d5ee-195">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-195">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="1d5ee-196">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-196">Int32</span></span>|  
|<span data-ttu-id="1d5ee-197">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-197">COLUMN_SORTID</span></span>|<span data-ttu-id="1d5ee-198">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-198">Int32</span></span>|  
|<span data-ttu-id="1d5ee-199">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-199">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="1d5ee-200">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1d5ee-200">Byte[]</span></span>|  
|<span data-ttu-id="1d5ee-201">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-201">IS_COMPUTED</span></span>|<span data-ttu-id="1d5ee-202">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-202">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1d5ee-203">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-203">Procedures</span></span>  
  
|<span data-ttu-id="1d5ee-204">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-204">ColumnName</span></span>|<span data-ttu-id="1d5ee-205">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-205">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-206">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-206">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1d5ee-207">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-207">String</span></span>|  
|<span data-ttu-id="1d5ee-208">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-208">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-209">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-209">String</span></span>|  
|<span data-ttu-id="1d5ee-210">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-210">PROCEDURE_NAME</span></span>|<span data-ttu-id="1d5ee-211">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-211">String</span></span>|  
|<span data-ttu-id="1d5ee-212">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-212">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1d5ee-213">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-213">Int16</span></span>|  
|<span data-ttu-id="1d5ee-214">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-214">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1d5ee-215">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-215">String</span></span>|  
|<span data-ttu-id="1d5ee-216">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-216">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-217">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-217">String</span></span>|  
|<span data-ttu-id="1d5ee-218">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-218">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-219">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-219">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-220">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-220">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-221">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-221">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1d5ee-222">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1d5ee-222">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1d5ee-223">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-223">ColumnName</span></span>|<span data-ttu-id="1d5ee-224">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-224">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-225">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-225">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1d5ee-226">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-226">String</span></span>|  
|<span data-ttu-id="1d5ee-227">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-227">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-228">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-228">String</span></span>|  
|<span data-ttu-id="1d5ee-229">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-229">PROCEDURE_NAME</span></span>|<span data-ttu-id="1d5ee-230">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-230">String</span></span>|  
|<span data-ttu-id="1d5ee-231">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-231">PARAMETER_NAME</span></span>|<span data-ttu-id="1d5ee-232">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-232">String</span></span>|  
|<span data-ttu-id="1d5ee-233">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-233">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-234">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-234">Int32</span></span>|  
|<span data-ttu-id="1d5ee-235">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-235">PARAMETER_TYPE</span></span>|<span data-ttu-id="1d5ee-236">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-236">Int32</span></span>|  
|<span data-ttu-id="1d5ee-237">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-237">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="1d5ee-238">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-238">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-239">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-239">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="1d5ee-240">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-240">String</span></span>|  
|<span data-ttu-id="1d5ee-241">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-241">IS_NULLABLE</span></span>|<span data-ttu-id="1d5ee-242">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-242">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-243">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-243">DATA_TYPE</span></span>|<span data-ttu-id="1d5ee-244">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-244">Int32</span></span>|  
|<span data-ttu-id="1d5ee-245">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-245">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1d5ee-246">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-246">Int64</span></span>|  
|<span data-ttu-id="1d5ee-247">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-247">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1d5ee-248">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-248">Int64</span></span>|  
|<span data-ttu-id="1d5ee-249">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-249">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1d5ee-250">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-250">Int32</span></span>|  
|<span data-ttu-id="1d5ee-251">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-251">NUMERIC_SCALE</span></span>|<span data-ttu-id="1d5ee-252">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-252">Int16</span></span>|  
|<span data-ttu-id="1d5ee-253">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-253">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-254">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-254">String</span></span>|  
|<span data-ttu-id="1d5ee-255">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-255">TYPE_NAME</span></span>|<span data-ttu-id="1d5ee-256">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-256">String</span></span>|  
|<span data-ttu-id="1d5ee-257">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-257">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="1d5ee-258">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-258">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="1d5ee-259">카탈로그</span><span class="sxs-lookup"><span data-stu-id="1d5ee-259">Catalog</span></span>  
  
|<span data-ttu-id="1d5ee-260">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-260">ColumnName</span></span>|<span data-ttu-id="1d5ee-261">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-261">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-262">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-262">CATALOG_NAME</span></span>|<span data-ttu-id="1d5ee-263">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-263">String</span></span>|  
|<span data-ttu-id="1d5ee-264">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-264">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-265">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-265">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1d5ee-266">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-266">Indexes</span></span>  
  
|<span data-ttu-id="1d5ee-267">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-267">ColumnName</span></span>|<span data-ttu-id="1d5ee-268">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-268">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-269">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-269">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-270">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-270">String</span></span>|  
|<span data-ttu-id="1d5ee-271">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-271">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-272">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-272">String</span></span>|  
|<span data-ttu-id="1d5ee-273">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-273">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-274">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-274">String</span></span>|  
|<span data-ttu-id="1d5ee-275">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-275">INDEX_CATALOG</span></span>|<span data-ttu-id="1d5ee-276">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-276">String</span></span>|  
|<span data-ttu-id="1d5ee-277">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-277">INDEX_SCHEMA</span></span>|<span data-ttu-id="1d5ee-278">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-278">String</span></span>|  
|<span data-ttu-id="1d5ee-279">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-279">INDEX_NAME</span></span>|<span data-ttu-id="1d5ee-280">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-280">String</span></span>|  
|<span data-ttu-id="1d5ee-281">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-281">PRIMARY_KEY</span></span>|<span data-ttu-id="1d5ee-282">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-282">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-283">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-283">UNIQUE</span></span>|<span data-ttu-id="1d5ee-284">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-284">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-285">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-285">CLUSTERED</span></span>|<span data-ttu-id="1d5ee-286">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-286">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-287">TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-287">TYPE</span></span>|<span data-ttu-id="1d5ee-288">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-288">Int32</span></span>|  
|<span data-ttu-id="1d5ee-289">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1d5ee-289">FILL_FACTOR</span></span>|<span data-ttu-id="1d5ee-290">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-290">Int32</span></span>|  
|<span data-ttu-id="1d5ee-291">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-291">INITIAL_SIZE</span></span>|<span data-ttu-id="1d5ee-292">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-292">Int32</span></span>|  
|<span data-ttu-id="1d5ee-293">NULLS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-293">NULLS</span></span>|<span data-ttu-id="1d5ee-294">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-294">Int32</span></span>|  
|<span data-ttu-id="1d5ee-295">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-295">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1d5ee-296">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-296">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-297">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-297">AUTO_UPDATE</span></span>|<span data-ttu-id="1d5ee-298">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-298">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-299">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-299">NULL_COLLATION</span></span>|<span data-ttu-id="1d5ee-300">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-300">Int32</span></span>|  
|<span data-ttu-id="1d5ee-301">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-301">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-302">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-302">Int64</span></span>|  
|<span data-ttu-id="1d5ee-303">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-303">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-304">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-304">String</span></span>|  
|<span data-ttu-id="1d5ee-305">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-305">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-306">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-306">Guid</span></span>|  
|<span data-ttu-id="1d5ee-307">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-307">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-308">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-308">Int64</span></span>|  
|<span data-ttu-id="1d5ee-309">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-309">COLLATION</span></span>|<span data-ttu-id="1d5ee-310">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-310">Int16</span></span>|  
|<span data-ttu-id="1d5ee-311">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-311">CARDINALITY</span></span>|<span data-ttu-id="1d5ee-312">Decimal</span><span class="sxs-lookup"><span data-stu-id="1d5ee-312">Decimal</span></span>|  
|<span data-ttu-id="1d5ee-313">PAGES</span><span class="sxs-lookup"><span data-stu-id="1d5ee-313">PAGES</span></span>|<span data-ttu-id="1d5ee-314">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-314">Int32</span></span>|  
|<span data-ttu-id="1d5ee-315">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-315">FILTER_CONDITION</span></span>|<span data-ttu-id="1d5ee-316">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-316">String</span></span>|  
|<span data-ttu-id="1d5ee-317">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-317">INTEGRATED</span></span>|<span data-ttu-id="1d5ee-318">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-318">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="1d5ee-319">Microsoft Oracle OLE DB</span><span class="sxs-lookup"><span data-stu-id="1d5ee-319">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="1d5ee-320">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="1d5ee-320">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="1d5ee-321">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-321">Tables</span></span>  
  
- <span data-ttu-id="1d5ee-322">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-322">Columns</span></span>  
  
- <span data-ttu-id="1d5ee-323">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-323">Procedures</span></span>  
  
- <span data-ttu-id="1d5ee-324">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1d5ee-324">ProcedureColumns</span></span>  
  
- <span data-ttu-id="1d5ee-325">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1d5ee-325">ProcedureParameters</span></span>  
  
- <span data-ttu-id="1d5ee-326">보기</span><span class="sxs-lookup"><span data-stu-id="1d5ee-326">Views</span></span>  
  
- <span data-ttu-id="1d5ee-327">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-327">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1d5ee-328">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-328">Tables</span></span>  
  
|<span data-ttu-id="1d5ee-329">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-329">ColumnName</span></span>|<span data-ttu-id="1d5ee-330">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-330">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-331">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-331">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-332">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-332">String</span></span>|  
|<span data-ttu-id="1d5ee-333">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-333">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-334">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-334">String</span></span>|  
|<span data-ttu-id="1d5ee-335">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-335">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-336">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-336">String</span></span>|  
|<span data-ttu-id="1d5ee-337">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-337">TABLE_TYPE</span></span>|<span data-ttu-id="1d5ee-338">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-338">String</span></span>|  
|<span data-ttu-id="1d5ee-339">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-339">TABLE_GUID</span></span>|<span data-ttu-id="1d5ee-340">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-340">Guid</span></span>|  
|<span data-ttu-id="1d5ee-341">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-341">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-342">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-342">String</span></span>|  
|<span data-ttu-id="1d5ee-343">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-343">TABLE_PROPID</span></span>|<span data-ttu-id="1d5ee-344">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-344">Int64</span></span>|  
|<span data-ttu-id="1d5ee-345">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-345">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-346">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-346">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-347">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-347">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-348">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-348">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1d5ee-349">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-349">Columns</span></span>  
  
|<span data-ttu-id="1d5ee-350">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-350">ColumnName</span></span>|<span data-ttu-id="1d5ee-351">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-351">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-352">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-352">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-353">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-353">String</span></span>|  
|<span data-ttu-id="1d5ee-354">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-354">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-355">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-355">String</span></span>|  
|<span data-ttu-id="1d5ee-356">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-356">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-357">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-357">String</span></span>|  
|<span data-ttu-id="1d5ee-358">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-358">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-359">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-359">String</span></span>|  
|<span data-ttu-id="1d5ee-360">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-360">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-361">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-361">Guid</span></span>|  
|<span data-ttu-id="1d5ee-362">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-362">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-363">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-363">Int64</span></span>|  
|<span data-ttu-id="1d5ee-364">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-364">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-365">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-365">Int64</span></span>|  
|<span data-ttu-id="1d5ee-366">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-366">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1d5ee-367">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-367">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-368">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-368">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1d5ee-369">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-369">String</span></span>|  
|<span data-ttu-id="1d5ee-370">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-370">COLUMN_FLAGS</span></span>|<span data-ttu-id="1d5ee-371">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-371">Int64</span></span>|  
|<span data-ttu-id="1d5ee-372">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-372">IS_NULLABLE</span></span>|<span data-ttu-id="1d5ee-373">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-373">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-374">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-374">DATA_TYPE</span></span>|<span data-ttu-id="1d5ee-375">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-375">Int32</span></span>|  
|<span data-ttu-id="1d5ee-376">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-376">TYPE_GUID</span></span>|<span data-ttu-id="1d5ee-377">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-377">Guid</span></span>|  
|<span data-ttu-id="1d5ee-378">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-378">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1d5ee-379">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-379">Int64</span></span>|  
|<span data-ttu-id="1d5ee-380">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-380">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1d5ee-381">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-381">Int64</span></span>|  
|<span data-ttu-id="1d5ee-382">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-382">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1d5ee-383">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-383">Int32</span></span>|  
|<span data-ttu-id="1d5ee-384">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-384">NUMERIC_SCALE</span></span>|<span data-ttu-id="1d5ee-385">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-385">Int16</span></span>|  
|<span data-ttu-id="1d5ee-386">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-386">DATETIME_PRECISION</span></span>|<span data-ttu-id="1d5ee-387">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-387">Int64</span></span>|  
|<span data-ttu-id="1d5ee-388">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-388">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1d5ee-389">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-389">String</span></span>|  
|<span data-ttu-id="1d5ee-390">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-390">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1d5ee-391">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-391">String</span></span>|  
|<span data-ttu-id="1d5ee-392">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-392">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1d5ee-393">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-393">String</span></span>|  
|<span data-ttu-id="1d5ee-394">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-394">COLLATION_CATALOG</span></span>|<span data-ttu-id="1d5ee-395">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-395">String</span></span>|  
|<span data-ttu-id="1d5ee-396">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-396">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1d5ee-397">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-397">String</span></span>|  
|<span data-ttu-id="1d5ee-398">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-398">COLLATION_NAME</span></span>|<span data-ttu-id="1d5ee-399">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-399">String</span></span>|  
|<span data-ttu-id="1d5ee-400">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-400">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1d5ee-401">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-401">String</span></span>|  
|<span data-ttu-id="1d5ee-402">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-402">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1d5ee-403">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-403">String</span></span>|  
|<span data-ttu-id="1d5ee-404">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-404">DOMAIN_NAME</span></span>|<span data-ttu-id="1d5ee-405">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-405">String</span></span>|  
|<span data-ttu-id="1d5ee-406">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-406">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-407">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-407">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1d5ee-408">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-408">Procedures</span></span>  
  
|<span data-ttu-id="1d5ee-409">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-409">ColumnName</span></span>|<span data-ttu-id="1d5ee-410">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-410">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-411">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-411">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1d5ee-412">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-412">String</span></span>|  
|<span data-ttu-id="1d5ee-413">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-413">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-414">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-414">String</span></span>|  
|<span data-ttu-id="1d5ee-415">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-415">PROCEDURE_NAME</span></span>|<span data-ttu-id="1d5ee-416">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-416">String</span></span>|  
|<span data-ttu-id="1d5ee-417">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-417">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1d5ee-418">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-418">Int16</span></span>|  
|<span data-ttu-id="1d5ee-419">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-419">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1d5ee-420">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-420">String</span></span>|  
|<span data-ttu-id="1d5ee-421">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-421">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-422">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-422">String</span></span>|  
|<span data-ttu-id="1d5ee-423">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-423">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-424">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-424">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-425">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-425">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-426">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-426">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="1d5ee-427">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1d5ee-427">ProcedureColumns</span></span>  
  
|<span data-ttu-id="1d5ee-428">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-428">ColumnName</span></span>|<span data-ttu-id="1d5ee-429">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-429">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-430">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-430">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1d5ee-431">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-431">String</span></span>|  
|<span data-ttu-id="1d5ee-432">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-432">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-433">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-433">String</span></span>|  
|<span data-ttu-id="1d5ee-434">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-434">PROCEDURE_NAME</span></span>|<span data-ttu-id="1d5ee-435">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-435">String</span></span>|  
|<span data-ttu-id="1d5ee-436">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-436">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-437">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-437">String</span></span>|  
|<span data-ttu-id="1d5ee-438">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-438">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-439">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-439">Guid</span></span>|  
|<span data-ttu-id="1d5ee-440">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-440">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-441">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-441">Int64</span></span>|  
|<span data-ttu-id="1d5ee-442">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="1d5ee-442">ROWSET_NUMBER</span></span>|<span data-ttu-id="1d5ee-443">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-443">Int64</span></span>|  
|<span data-ttu-id="1d5ee-444">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-444">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-445">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-445">Int64</span></span>|  
|<span data-ttu-id="1d5ee-446">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-446">IS_NULLABLE</span></span>|<span data-ttu-id="1d5ee-447">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-447">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-448">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-448">DATA_TYPE</span></span>|<span data-ttu-id="1d5ee-449">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-449">Int32</span></span>|  
|<span data-ttu-id="1d5ee-450">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-450">TYPE_GUID</span></span>|<span data-ttu-id="1d5ee-451">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-451">Guid</span></span>|  
|<span data-ttu-id="1d5ee-452">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-452">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1d5ee-453">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-453">Int64</span></span>|  
|<span data-ttu-id="1d5ee-454">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-454">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1d5ee-455">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-455">Int64</span></span>|  
|<span data-ttu-id="1d5ee-456">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-456">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1d5ee-457">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-457">Int32</span></span>|  
|<span data-ttu-id="1d5ee-458">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-458">NUMERIC_SCALE</span></span>|<span data-ttu-id="1d5ee-459">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-459">Int16</span></span>|  
|<span data-ttu-id="1d5ee-460">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-460">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-461">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-461">String</span></span>|  
|<span data-ttu-id="1d5ee-462">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="1d5ee-462">OVERLOAD</span></span>|<span data-ttu-id="1d5ee-463">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-463">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1d5ee-464">보기</span><span class="sxs-lookup"><span data-stu-id="1d5ee-464">Views</span></span>  
  
|<span data-ttu-id="1d5ee-465">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-465">ColumnName</span></span>|<span data-ttu-id="1d5ee-466">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-466">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-467">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-467">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-468">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-468">String</span></span>|  
|<span data-ttu-id="1d5ee-469">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-469">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-470">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-470">String</span></span>|  
|<span data-ttu-id="1d5ee-471">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-471">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-472">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-472">String</span></span>|  
|<span data-ttu-id="1d5ee-473">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-473">VIEW_DEFINITION</span></span>|<span data-ttu-id="1d5ee-474">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-474">String</span></span>|  
|<span data-ttu-id="1d5ee-475">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-475">CHECK_OPTION</span></span>|<span data-ttu-id="1d5ee-476">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-476">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-477">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-477">IS_UPDATABLE</span></span>|<span data-ttu-id="1d5ee-478">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-478">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-479">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-479">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-480">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-480">String</span></span>|  
|<span data-ttu-id="1d5ee-481">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-481">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-482">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-482">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-483">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-483">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-484">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-484">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1d5ee-485">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-485">Indexes</span></span>  
  
|<span data-ttu-id="1d5ee-486">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-486">ColumnName</span></span>|<span data-ttu-id="1d5ee-487">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-487">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-488">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-488">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-489">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-489">String</span></span>|  
|<span data-ttu-id="1d5ee-490">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-490">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-491">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-491">String</span></span>|  
|<span data-ttu-id="1d5ee-492">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-492">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-493">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-493">String</span></span>|  
|<span data-ttu-id="1d5ee-494">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-494">INDEX_CATALOG</span></span>|<span data-ttu-id="1d5ee-495">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-495">String</span></span>|  
|<span data-ttu-id="1d5ee-496">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-496">INDEX_SCHEMA</span></span>|<span data-ttu-id="1d5ee-497">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-497">String</span></span>|  
|<span data-ttu-id="1d5ee-498">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-498">INDEX_NAME</span></span>|<span data-ttu-id="1d5ee-499">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-499">String</span></span>|  
|<span data-ttu-id="1d5ee-500">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-500">PRIMARY_KEY</span></span>|<span data-ttu-id="1d5ee-501">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-501">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-502">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-502">UNIQUE</span></span>|<span data-ttu-id="1d5ee-503">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-503">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-504">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-504">CLUSTERED</span></span>|<span data-ttu-id="1d5ee-505">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-505">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-506">TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-506">TYPE</span></span>|<span data-ttu-id="1d5ee-507">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-507">Int32</span></span>|  
|<span data-ttu-id="1d5ee-508">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1d5ee-508">FILL_FACTOR</span></span>|<span data-ttu-id="1d5ee-509">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-509">Int32</span></span>|  
|<span data-ttu-id="1d5ee-510">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-510">INITIAL_SIZE</span></span>|<span data-ttu-id="1d5ee-511">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-511">Int32</span></span>|  
|<span data-ttu-id="1d5ee-512">NULLS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-512">NULLS</span></span>|<span data-ttu-id="1d5ee-513">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-513">Int32</span></span>|  
|<span data-ttu-id="1d5ee-514">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-514">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1d5ee-515">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-515">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-516">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-516">AUTO_UPDATE</span></span>|<span data-ttu-id="1d5ee-517">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-517">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-518">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-518">NULL_COLLATION</span></span>|<span data-ttu-id="1d5ee-519">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-519">Int32</span></span>|  
|<span data-ttu-id="1d5ee-520">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-520">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-521">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-521">Int64</span></span>|  
|<span data-ttu-id="1d5ee-522">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-522">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-523">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-523">String</span></span>|  
|<span data-ttu-id="1d5ee-524">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-524">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-525">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-525">Guid</span></span>|  
|<span data-ttu-id="1d5ee-526">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-526">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-527">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-527">Int64</span></span>|  
|<span data-ttu-id="1d5ee-528">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-528">COLLATION</span></span>|<span data-ttu-id="1d5ee-529">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-529">Int16</span></span>|  
|<span data-ttu-id="1d5ee-530">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-530">CARDINALITY</span></span>|<span data-ttu-id="1d5ee-531">Decimal</span><span class="sxs-lookup"><span data-stu-id="1d5ee-531">Decimal</span></span>|  
|<span data-ttu-id="1d5ee-532">PAGES</span><span class="sxs-lookup"><span data-stu-id="1d5ee-532">PAGES</span></span>|<span data-ttu-id="1d5ee-533">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-533">Int32</span></span>|  
|<span data-ttu-id="1d5ee-534">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-534">FILTER_CONDITION</span></span>|<span data-ttu-id="1d5ee-535">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-535">String</span></span>|  
|<span data-ttu-id="1d5ee-536">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-536">INTEGRATED</span></span>|<span data-ttu-id="1d5ee-537">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-537">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="1d5ee-538">Microsoft Jet OLE DB</span><span class="sxs-lookup"><span data-stu-id="1d5ee-538">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="1d5ee-539">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="1d5ee-539">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="1d5ee-540">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-540">Tables</span></span>  
  
- <span data-ttu-id="1d5ee-541">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-541">Columns</span></span>  
  
- <span data-ttu-id="1d5ee-542">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-542">Procedures</span></span>  
  
- <span data-ttu-id="1d5ee-543">보기</span><span class="sxs-lookup"><span data-stu-id="1d5ee-543">Views</span></span>  
  
- <span data-ttu-id="1d5ee-544">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-544">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1d5ee-545">테이블</span><span class="sxs-lookup"><span data-stu-id="1d5ee-545">Tables</span></span>  
  
|<span data-ttu-id="1d5ee-546">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-546">ColumnName</span></span>|<span data-ttu-id="1d5ee-547">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-547">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-548">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-548">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-549">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-549">String</span></span>|  
|<span data-ttu-id="1d5ee-550">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-550">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-551">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-551">String</span></span>|  
|<span data-ttu-id="1d5ee-552">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-552">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-553">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-553">String</span></span>|  
|<span data-ttu-id="1d5ee-554">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-554">TABLE_TYPE</span></span>|<span data-ttu-id="1d5ee-555">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-555">String</span></span>|  
|<span data-ttu-id="1d5ee-556">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-556">TABLE_GUID</span></span>|<span data-ttu-id="1d5ee-557">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-557">Guid</span></span>|  
|<span data-ttu-id="1d5ee-558">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-558">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-559">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-559">String</span></span>|  
|<span data-ttu-id="1d5ee-560">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-560">TABLE_PROPID</span></span>|<span data-ttu-id="1d5ee-561">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-561">Int64</span></span>|  
|<span data-ttu-id="1d5ee-562">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-562">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-563">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-563">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-564">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-564">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-565">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-565">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1d5ee-566">열</span><span class="sxs-lookup"><span data-stu-id="1d5ee-566">Columns</span></span>  
  
|<span data-ttu-id="1d5ee-567">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-567">ColumnName</span></span>|<span data-ttu-id="1d5ee-568">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-568">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-569">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-569">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-570">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-570">String</span></span>|  
|<span data-ttu-id="1d5ee-571">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-571">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-572">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-572">String</span></span>|  
|<span data-ttu-id="1d5ee-573">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-573">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-574">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-574">String</span></span>|  
|<span data-ttu-id="1d5ee-575">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-575">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-576">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-576">String</span></span>|  
|<span data-ttu-id="1d5ee-577">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-577">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-578">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-578">Guid</span></span>|  
|<span data-ttu-id="1d5ee-579">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-579">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-580">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-580">Int64</span></span>|  
|<span data-ttu-id="1d5ee-581">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-581">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-582">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-582">Int64</span></span>|  
|<span data-ttu-id="1d5ee-583">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-583">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1d5ee-584">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-584">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-585">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1d5ee-585">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1d5ee-586">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-586">String</span></span>|  
|<span data-ttu-id="1d5ee-587">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-587">COLUMN_FLAGS</span></span>|<span data-ttu-id="1d5ee-588">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-588">Int64</span></span>|  
|<span data-ttu-id="1d5ee-589">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-589">IS_NULLABLE</span></span>|<span data-ttu-id="1d5ee-590">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-590">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-591">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-591">DATA_TYPE</span></span>|<span data-ttu-id="1d5ee-592">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-592">Int32</span></span>|  
|<span data-ttu-id="1d5ee-593">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-593">TYPE_GUID</span></span>|<span data-ttu-id="1d5ee-594">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-594">Guid</span></span>|  
|<span data-ttu-id="1d5ee-595">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-595">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1d5ee-596">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-596">Int64</span></span>|  
|<span data-ttu-id="1d5ee-597">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1d5ee-597">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1d5ee-598">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-598">Int64</span></span>|  
|<span data-ttu-id="1d5ee-599">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-599">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1d5ee-600">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-600">Int32</span></span>|  
|<span data-ttu-id="1d5ee-601">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-601">NUMERIC_SCALE</span></span>|<span data-ttu-id="1d5ee-602">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-602">Int16</span></span>|  
|<span data-ttu-id="1d5ee-603">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-603">DATETIME_PRECISION</span></span>|<span data-ttu-id="1d5ee-604">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-604">Int64</span></span>|  
|<span data-ttu-id="1d5ee-605">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-605">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1d5ee-606">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-606">String</span></span>|  
|<span data-ttu-id="1d5ee-607">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-607">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1d5ee-608">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-608">String</span></span>|  
|<span data-ttu-id="1d5ee-609">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-609">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1d5ee-610">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-610">String</span></span>|  
|<span data-ttu-id="1d5ee-611">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-611">COLLATION_CATALOG</span></span>|<span data-ttu-id="1d5ee-612">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-612">String</span></span>|  
|<span data-ttu-id="1d5ee-613">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-613">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1d5ee-614">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-614">String</span></span>|  
|<span data-ttu-id="1d5ee-615">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-615">COLLATION_NAME</span></span>|<span data-ttu-id="1d5ee-616">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-616">String</span></span>|  
|<span data-ttu-id="1d5ee-617">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-617">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1d5ee-618">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-618">String</span></span>|  
|<span data-ttu-id="1d5ee-619">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-619">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1d5ee-620">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-620">String</span></span>|  
|<span data-ttu-id="1d5ee-621">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-621">DOMAIN_NAME</span></span>|<span data-ttu-id="1d5ee-622">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-622">String</span></span>|  
|<span data-ttu-id="1d5ee-623">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-623">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-624">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-624">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1d5ee-625">프로시저</span><span class="sxs-lookup"><span data-stu-id="1d5ee-625">Procedures</span></span>  
  
|<span data-ttu-id="1d5ee-626">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-626">ColumnName</span></span>|<span data-ttu-id="1d5ee-627">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-627">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-628">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-628">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1d5ee-629">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-629">String</span></span>|  
|<span data-ttu-id="1d5ee-630">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-630">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-631">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-631">String</span></span>|  
|<span data-ttu-id="1d5ee-632">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-632">PROCEDURE_NAME</span></span>|<span data-ttu-id="1d5ee-633">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-633">String</span></span>|  
|<span data-ttu-id="1d5ee-634">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-634">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1d5ee-635">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-635">Int16</span></span>|  
|<span data-ttu-id="1d5ee-636">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-636">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1d5ee-637">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-637">String</span></span>|  
|<span data-ttu-id="1d5ee-638">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-638">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-639">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-639">String</span></span>|  
|<span data-ttu-id="1d5ee-640">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-640">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-641">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-641">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-642">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-642">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-643">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-643">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1d5ee-644">보기</span><span class="sxs-lookup"><span data-stu-id="1d5ee-644">Views</span></span>  
  
|<span data-ttu-id="1d5ee-645">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-645">ColumnName</span></span>|<span data-ttu-id="1d5ee-646">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-646">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-647">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-647">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-648">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-648">String</span></span>|  
|<span data-ttu-id="1d5ee-649">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-649">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-650">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-650">String</span></span>|  
|<span data-ttu-id="1d5ee-651">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-651">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-652">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-652">String</span></span>|  
|<span data-ttu-id="1d5ee-653">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-653">VIEW_DEFINITION</span></span>|<span data-ttu-id="1d5ee-654">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-654">String</span></span>|  
|<span data-ttu-id="1d5ee-655">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-655">CHECK_OPTION</span></span>|<span data-ttu-id="1d5ee-656">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-656">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-657">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-657">IS_UPDATABLE</span></span>|<span data-ttu-id="1d5ee-658">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-658">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-659">설명</span><span class="sxs-lookup"><span data-stu-id="1d5ee-659">DESCRIPTION</span></span>|<span data-ttu-id="1d5ee-660">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-660">String</span></span>|  
|<span data-ttu-id="1d5ee-661">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-661">DATE_CREATED</span></span>|<span data-ttu-id="1d5ee-662">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-662">DateTime</span></span>|  
|<span data-ttu-id="1d5ee-663">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-663">DATE_MODIFIED</span></span>|<span data-ttu-id="1d5ee-664">DateTime</span><span class="sxs-lookup"><span data-stu-id="1d5ee-664">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1d5ee-665">인덱스</span><span class="sxs-lookup"><span data-stu-id="1d5ee-665">Indexes</span></span>  
  
|<span data-ttu-id="1d5ee-666">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1d5ee-666">ColumnName</span></span>|<span data-ttu-id="1d5ee-667">DataType</span><span class="sxs-lookup"><span data-stu-id="1d5ee-667">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1d5ee-668">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-668">TABLE_CATALOG</span></span>|<span data-ttu-id="1d5ee-669">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-669">String</span></span>|  
|<span data-ttu-id="1d5ee-670">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-670">TABLE_SCHEMA</span></span>|<span data-ttu-id="1d5ee-671">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-671">String</span></span>|  
|<span data-ttu-id="1d5ee-672">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-672">TABLE_NAME</span></span>|<span data-ttu-id="1d5ee-673">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-673">String</span></span>|  
|<span data-ttu-id="1d5ee-674">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1d5ee-674">INDEX_CATALOG</span></span>|<span data-ttu-id="1d5ee-675">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-675">String</span></span>|  
|<span data-ttu-id="1d5ee-676">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1d5ee-676">INDEX_SCHEMA</span></span>|<span data-ttu-id="1d5ee-677">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-677">String</span></span>|  
|<span data-ttu-id="1d5ee-678">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-678">INDEX_NAME</span></span>|<span data-ttu-id="1d5ee-679">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-679">String</span></span>|  
|<span data-ttu-id="1d5ee-680">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-680">PRIMARY_KEY</span></span>|<span data-ttu-id="1d5ee-681">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-681">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-682">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-682">UNIQUE</span></span>|<span data-ttu-id="1d5ee-683">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-683">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-684">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-684">CLUSTERED</span></span>|<span data-ttu-id="1d5ee-685">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-685">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-686">TYPE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-686">TYPE</span></span>|<span data-ttu-id="1d5ee-687">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-687">Int32</span></span>|  
|<span data-ttu-id="1d5ee-688">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1d5ee-688">FILL_FACTOR</span></span>|<span data-ttu-id="1d5ee-689">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-689">Int32</span></span>|  
|<span data-ttu-id="1d5ee-690">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-690">INITIAL_SIZE</span></span>|<span data-ttu-id="1d5ee-691">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-691">Int32</span></span>|  
|<span data-ttu-id="1d5ee-692">NULLS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-692">NULLS</span></span>|<span data-ttu-id="1d5ee-693">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-693">Int32</span></span>|  
|<span data-ttu-id="1d5ee-694">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1d5ee-694">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1d5ee-695">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-695">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-696">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1d5ee-696">AUTO_UPDATE</span></span>|<span data-ttu-id="1d5ee-697">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-697">Boolean</span></span>|  
|<span data-ttu-id="1d5ee-698">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-698">NULL_COLLATION</span></span>|<span data-ttu-id="1d5ee-699">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-699">Int32</span></span>|  
|<span data-ttu-id="1d5ee-700">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-700">ORDINAL_POSITION</span></span>|<span data-ttu-id="1d5ee-701">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-701">Int64</span></span>|  
|<span data-ttu-id="1d5ee-702">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1d5ee-702">COLUMN_NAME</span></span>|<span data-ttu-id="1d5ee-703">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-703">String</span></span>|  
|<span data-ttu-id="1d5ee-704">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-704">COLUMN_GUID</span></span>|<span data-ttu-id="1d5ee-705">GUID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-705">Guid</span></span>|  
|<span data-ttu-id="1d5ee-706">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1d5ee-706">COLUMN_PROPID</span></span>|<span data-ttu-id="1d5ee-707">Int64</span><span class="sxs-lookup"><span data-stu-id="1d5ee-707">Int64</span></span>|  
|<span data-ttu-id="1d5ee-708">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-708">COLLATION</span></span>|<span data-ttu-id="1d5ee-709">Int16</span><span class="sxs-lookup"><span data-stu-id="1d5ee-709">Int16</span></span>|  
|<span data-ttu-id="1d5ee-710">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1d5ee-710">CARDINALITY</span></span>|<span data-ttu-id="1d5ee-711">Decimal</span><span class="sxs-lookup"><span data-stu-id="1d5ee-711">Decimal</span></span>|  
|<span data-ttu-id="1d5ee-712">PAGES</span><span class="sxs-lookup"><span data-stu-id="1d5ee-712">PAGES</span></span>|<span data-ttu-id="1d5ee-713">Int32</span><span class="sxs-lookup"><span data-stu-id="1d5ee-713">Int32</span></span>|  
|<span data-ttu-id="1d5ee-714">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1d5ee-714">FILTER_CONDITION</span></span>|<span data-ttu-id="1d5ee-715">String</span><span class="sxs-lookup"><span data-stu-id="1d5ee-715">String</span></span>|  
|<span data-ttu-id="1d5ee-716">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1d5ee-716">INTEGRATED</span></span>|<span data-ttu-id="1d5ee-717">부울</span><span class="sxs-lookup"><span data-stu-id="1d5ee-717">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d5ee-718">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d5ee-718">See also</span></span>

- [<span data-ttu-id="1d5ee-719">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="1d5ee-719">ADO.NET Overview</span></span>](ado-net-overview.md)
