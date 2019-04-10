---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164686"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="07496-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="07496-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="07496-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07496-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="07496-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="07496-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="07496-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07496-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="07496-106">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-106">Tables</span></span>  
  
-   <span data-ttu-id="07496-107">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-107">Columns</span></span>  
  
-   <span data-ttu-id="07496-108">절차</span><span class="sxs-lookup"><span data-stu-id="07496-108">Procedures</span></span>  
  
-   <span data-ttu-id="07496-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="07496-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="07496-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="07496-110">Catalog</span></span>  
  
-   <span data-ttu-id="07496-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="07496-112">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-112">Tables</span></span>  
  
|<span data-ttu-id="07496-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-113">ColumnName</span></span>|<span data-ttu-id="07496-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-115">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-116">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-116">String</span></span>|  
|<span data-ttu-id="07496-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-118">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-118">String</span></span>|  
|<span data-ttu-id="07496-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-119">TABLE_NAME</span></span>|<span data-ttu-id="07496-120">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-120">String</span></span>|  
|<span data-ttu-id="07496-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-121">TABLE_TYPE</span></span>|<span data-ttu-id="07496-122">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-122">String</span></span>|  
|<span data-ttu-id="07496-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-123">TABLE_GUID</span></span>|<span data-ttu-id="07496-124">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-124">Guid</span></span>|  
|<span data-ttu-id="07496-125">설명</span><span class="sxs-lookup"><span data-stu-id="07496-125">DESCRIPTION</span></span>|<span data-ttu-id="07496-126">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-126">String</span></span>|  
|<span data-ttu-id="07496-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-127">TABLE_PROPID</span></span>|<span data-ttu-id="07496-128">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-128">Int64</span></span>|  
|<span data-ttu-id="07496-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-129">DATE_CREATED</span></span>|<span data-ttu-id="07496-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-130">DateTime</span></span>|  
|<span data-ttu-id="07496-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-131">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="07496-133">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-133">Columns</span></span>  
  
|<span data-ttu-id="07496-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-134">ColumnName</span></span>|<span data-ttu-id="07496-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-136">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-137">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-137">String</span></span>|  
|<span data-ttu-id="07496-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-139">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-139">String</span></span>|  
|<span data-ttu-id="07496-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-140">TABLE_NAME</span></span>|<span data-ttu-id="07496-141">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-141">String</span></span>|  
|<span data-ttu-id="07496-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-142">COLUMN_NAME</span></span>|<span data-ttu-id="07496-143">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-143">String</span></span>|  
|<span data-ttu-id="07496-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-144">COLUMN_GUID</span></span>|<span data-ttu-id="07496-145">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-145">Guid</span></span>|  
|<span data-ttu-id="07496-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-146">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-147">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-147">Int64</span></span>|  
|<span data-ttu-id="07496-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-149">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-149">Int64</span></span>|  
|<span data-ttu-id="07496-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="07496-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-151">Boolean</span></span>|  
|<span data-ttu-id="07496-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="07496-153">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-153">String</span></span>|  
|<span data-ttu-id="07496-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="07496-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="07496-155">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-155">Int64</span></span>|  
|<span data-ttu-id="07496-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="07496-156">IS_NULLABLE</span></span>|<span data-ttu-id="07496-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-157">Boolean</span></span>|  
|<span data-ttu-id="07496-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-158">DATA_TYPE</span></span>|<span data-ttu-id="07496-159">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-159">Int32</span></span>|  
|<span data-ttu-id="07496-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-160">TYPE_GUID</span></span>|<span data-ttu-id="07496-161">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-161">Guid</span></span>|  
|<span data-ttu-id="07496-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="07496-163">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-163">Int64</span></span>|  
|<span data-ttu-id="07496-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="07496-165">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-165">Int64</span></span>|  
|<span data-ttu-id="07496-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="07496-167">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-167">Int32</span></span>|  
|<span data-ttu-id="07496-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="07496-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="07496-169">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-169">Int16</span></span>|  
|<span data-ttu-id="07496-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="07496-171">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-171">Int64</span></span>|  
|<span data-ttu-id="07496-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="07496-173">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-173">String</span></span>|  
|<span data-ttu-id="07496-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="07496-175">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-175">String</span></span>|  
|<span data-ttu-id="07496-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="07496-177">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-177">String</span></span>|  
|<span data-ttu-id="07496-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="07496-179">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-179">String</span></span>|  
|<span data-ttu-id="07496-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="07496-181">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-181">String</span></span>|  
|<span data-ttu-id="07496-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-182">COLLATION_NAME</span></span>|<span data-ttu-id="07496-183">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-183">String</span></span>|  
|<span data-ttu-id="07496-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="07496-185">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-185">String</span></span>|  
|<span data-ttu-id="07496-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="07496-187">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-187">String</span></span>|  
|<span data-ttu-id="07496-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-188">DOMAIN_NAME</span></span>|<span data-ttu-id="07496-189">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-189">String</span></span>|  
|<span data-ttu-id="07496-190">설명</span><span class="sxs-lookup"><span data-stu-id="07496-190">DESCRIPTION</span></span>|<span data-ttu-id="07496-191">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-191">String</span></span>|  
|<span data-ttu-id="07496-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="07496-192">COLUMN_LCID</span></span>|<span data-ttu-id="07496-193">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-193">Int32</span></span>|  
|<span data-ttu-id="07496-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="07496-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="07496-195">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-195">Int32</span></span>|  
|<span data-ttu-id="07496-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="07496-196">COLUMN_SORTID</span></span>|<span data-ttu-id="07496-197">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-197">Int32</span></span>|  
|<span data-ttu-id="07496-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="07496-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="07496-199">Byte[]</span></span>|  
|<span data-ttu-id="07496-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="07496-200">IS_COMPUTED</span></span>|<span data-ttu-id="07496-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="07496-202">절차</span><span class="sxs-lookup"><span data-stu-id="07496-202">Procedures</span></span>  
  
|<span data-ttu-id="07496-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-203">ColumnName</span></span>|<span data-ttu-id="07496-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="07496-206">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-206">String</span></span>|  
|<span data-ttu-id="07496-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="07496-208">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-208">String</span></span>|  
|<span data-ttu-id="07496-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="07496-210">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-210">String</span></span>|  
|<span data-ttu-id="07496-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="07496-212">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-212">Int16</span></span>|  
|<span data-ttu-id="07496-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="07496-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="07496-214">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-214">String</span></span>|  
|<span data-ttu-id="07496-215">설명</span><span class="sxs-lookup"><span data-stu-id="07496-215">DESCRIPTION</span></span>|<span data-ttu-id="07496-216">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-216">String</span></span>|  
|<span data-ttu-id="07496-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-217">DATE_CREATED</span></span>|<span data-ttu-id="07496-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-218">DateTime</span></span>|  
|<span data-ttu-id="07496-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-219">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="07496-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="07496-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="07496-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-222">ColumnName</span></span>|<span data-ttu-id="07496-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="07496-225">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-225">String</span></span>|  
|<span data-ttu-id="07496-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="07496-227">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-227">String</span></span>|  
|<span data-ttu-id="07496-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="07496-229">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-229">String</span></span>|  
|<span data-ttu-id="07496-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-230">PARAMETER_NAME</span></span>|<span data-ttu-id="07496-231">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-231">String</span></span>|  
|<span data-ttu-id="07496-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-233">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-233">Int32</span></span>|  
|<span data-ttu-id="07496-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="07496-235">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-235">Int32</span></span>|  
|<span data-ttu-id="07496-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="07496-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-237">Boolean</span></span>|  
|<span data-ttu-id="07496-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="07496-239">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-239">String</span></span>|  
|<span data-ttu-id="07496-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="07496-240">IS_NULLABLE</span></span>|<span data-ttu-id="07496-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-241">Boolean</span></span>|  
|<span data-ttu-id="07496-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-242">DATA_TYPE</span></span>|<span data-ttu-id="07496-243">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-243">Int32</span></span>|  
|<span data-ttu-id="07496-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="07496-245">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-245">Int64</span></span>|  
|<span data-ttu-id="07496-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="07496-247">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-247">Int64</span></span>|  
|<span data-ttu-id="07496-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="07496-249">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-249">Int32</span></span>|  
|<span data-ttu-id="07496-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="07496-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="07496-251">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-251">Int16</span></span>|  
|<span data-ttu-id="07496-252">설명</span><span class="sxs-lookup"><span data-stu-id="07496-252">DESCRIPTION</span></span>|<span data-ttu-id="07496-253">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-253">String</span></span>|  
|<span data-ttu-id="07496-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-254">TYPE_NAME</span></span>|<span data-ttu-id="07496-255">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-255">String</span></span>|  
|<span data-ttu-id="07496-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="07496-257">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="07496-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="07496-258">Catalog</span></span>  
  
|<span data-ttu-id="07496-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-259">ColumnName</span></span>|<span data-ttu-id="07496-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-261">CATALOG_NAME</span></span>|<span data-ttu-id="07496-262">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-262">String</span></span>|  
|<span data-ttu-id="07496-263">설명</span><span class="sxs-lookup"><span data-stu-id="07496-263">DESCRIPTION</span></span>|<span data-ttu-id="07496-264">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="07496-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-265">Indexes</span></span>  
  
|<span data-ttu-id="07496-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-266">ColumnName</span></span>|<span data-ttu-id="07496-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-268">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-269">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-269">String</span></span>|  
|<span data-ttu-id="07496-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-271">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-271">String</span></span>|  
|<span data-ttu-id="07496-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-272">TABLE_NAME</span></span>|<span data-ttu-id="07496-273">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-273">String</span></span>|  
|<span data-ttu-id="07496-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-274">INDEX_CATALOG</span></span>|<span data-ttu-id="07496-275">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-275">String</span></span>|  
|<span data-ttu-id="07496-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="07496-277">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-277">String</span></span>|  
|<span data-ttu-id="07496-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-278">INDEX_NAME</span></span>|<span data-ttu-id="07496-279">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-279">String</span></span>|  
|<span data-ttu-id="07496-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="07496-280">PRIMARY_KEY</span></span>|<span data-ttu-id="07496-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-281">Boolean</span></span>|  
|<span data-ttu-id="07496-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="07496-282">UNIQUE</span></span>|<span data-ttu-id="07496-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-283">Boolean</span></span>|  
|<span data-ttu-id="07496-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="07496-284">CLUSTERED</span></span>|<span data-ttu-id="07496-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-285">Boolean</span></span>|  
|<span data-ttu-id="07496-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-286">TYPE</span></span>|<span data-ttu-id="07496-287">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-287">Int32</span></span>|  
|<span data-ttu-id="07496-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="07496-288">FILL_FACTOR</span></span>|<span data-ttu-id="07496-289">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-289">Int32</span></span>|  
|<span data-ttu-id="07496-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="07496-290">INITIAL_SIZE</span></span>|<span data-ttu-id="07496-291">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-291">Int32</span></span>|  
|<span data-ttu-id="07496-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="07496-292">NULLS</span></span>|<span data-ttu-id="07496-293">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-293">Int32</span></span>|  
|<span data-ttu-id="07496-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="07496-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="07496-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-295">Boolean</span></span>|  
|<span data-ttu-id="07496-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="07496-296">AUTO_UPDATE</span></span>|<span data-ttu-id="07496-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-297">Boolean</span></span>|  
|<span data-ttu-id="07496-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-298">NULL_COLLATION</span></span>|<span data-ttu-id="07496-299">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-299">Int32</span></span>|  
|<span data-ttu-id="07496-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-301">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-301">Int64</span></span>|  
|<span data-ttu-id="07496-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-302">COLUMN_NAME</span></span>|<span data-ttu-id="07496-303">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-303">String</span></span>|  
|<span data-ttu-id="07496-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-304">COLUMN_GUID</span></span>|<span data-ttu-id="07496-305">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-305">Guid</span></span>|  
|<span data-ttu-id="07496-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-306">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-307">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-307">Int64</span></span>|  
|<span data-ttu-id="07496-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-308">COLLATION</span></span>|<span data-ttu-id="07496-309">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-309">Int16</span></span>|  
|<span data-ttu-id="07496-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="07496-310">CARDINALITY</span></span>|<span data-ttu-id="07496-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="07496-311">Decimal</span></span>|  
|<span data-ttu-id="07496-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="07496-312">PAGES</span></span>|<span data-ttu-id="07496-313">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-313">Int32</span></span>|  
|<span data-ttu-id="07496-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="07496-314">FILTER_CONDITION</span></span>|<span data-ttu-id="07496-315">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-315">String</span></span>|  
|<span data-ttu-id="07496-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="07496-316">INTEGRATED</span></span>|<span data-ttu-id="07496-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="07496-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="07496-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="07496-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="07496-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="07496-320">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-320">Tables</span></span>  
  
-   <span data-ttu-id="07496-321">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-321">Columns</span></span>  
  
-   <span data-ttu-id="07496-322">절차</span><span class="sxs-lookup"><span data-stu-id="07496-322">Procedures</span></span>  
  
-   <span data-ttu-id="07496-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="07496-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="07496-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="07496-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="07496-325">보기</span><span class="sxs-lookup"><span data-stu-id="07496-325">Views</span></span>  
  
-   <span data-ttu-id="07496-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="07496-327">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-327">Tables</span></span>  
  
|<span data-ttu-id="07496-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-328">ColumnName</span></span>|<span data-ttu-id="07496-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-330">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-331">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-331">String</span></span>|  
|<span data-ttu-id="07496-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-333">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-333">String</span></span>|  
|<span data-ttu-id="07496-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-334">TABLE_NAME</span></span>|<span data-ttu-id="07496-335">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-335">String</span></span>|  
|<span data-ttu-id="07496-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-336">TABLE_TYPE</span></span>|<span data-ttu-id="07496-337">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-337">String</span></span>|  
|<span data-ttu-id="07496-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-338">TABLE_GUID</span></span>|<span data-ttu-id="07496-339">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-339">Guid</span></span>|  
|<span data-ttu-id="07496-340">설명</span><span class="sxs-lookup"><span data-stu-id="07496-340">DESCRIPTION</span></span>|<span data-ttu-id="07496-341">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-341">String</span></span>|  
|<span data-ttu-id="07496-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-342">TABLE_PROPID</span></span>|<span data-ttu-id="07496-343">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-343">Int64</span></span>|  
|<span data-ttu-id="07496-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-344">DATE_CREATED</span></span>|<span data-ttu-id="07496-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-345">DateTime</span></span>|  
|<span data-ttu-id="07496-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-346">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="07496-348">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-348">Columns</span></span>  
  
|<span data-ttu-id="07496-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-349">ColumnName</span></span>|<span data-ttu-id="07496-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-351">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-352">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-352">String</span></span>|  
|<span data-ttu-id="07496-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-354">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-354">String</span></span>|  
|<span data-ttu-id="07496-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-355">TABLE_NAME</span></span>|<span data-ttu-id="07496-356">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-356">String</span></span>|  
|<span data-ttu-id="07496-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-357">COLUMN_NAME</span></span>|<span data-ttu-id="07496-358">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-358">String</span></span>|  
|<span data-ttu-id="07496-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-359">COLUMN_GUID</span></span>|<span data-ttu-id="07496-360">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-360">Guid</span></span>|  
|<span data-ttu-id="07496-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-361">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-362">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-362">Int64</span></span>|  
|<span data-ttu-id="07496-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-364">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-364">Int64</span></span>|  
|<span data-ttu-id="07496-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="07496-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-366">Boolean</span></span>|  
|<span data-ttu-id="07496-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="07496-368">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-368">String</span></span>|  
|<span data-ttu-id="07496-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="07496-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="07496-370">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-370">Int64</span></span>|  
|<span data-ttu-id="07496-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="07496-371">IS_NULLABLE</span></span>|<span data-ttu-id="07496-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-372">Boolean</span></span>|  
|<span data-ttu-id="07496-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-373">DATA_TYPE</span></span>|<span data-ttu-id="07496-374">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-374">Int32</span></span>|  
|<span data-ttu-id="07496-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-375">TYPE_GUID</span></span>|<span data-ttu-id="07496-376">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-376">Guid</span></span>|  
|<span data-ttu-id="07496-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="07496-378">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-378">Int64</span></span>|  
|<span data-ttu-id="07496-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="07496-380">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-380">Int64</span></span>|  
|<span data-ttu-id="07496-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="07496-382">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-382">Int32</span></span>|  
|<span data-ttu-id="07496-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="07496-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="07496-384">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-384">Int16</span></span>|  
|<span data-ttu-id="07496-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="07496-386">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-386">Int64</span></span>|  
|<span data-ttu-id="07496-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="07496-388">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-388">String</span></span>|  
|<span data-ttu-id="07496-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="07496-390">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-390">String</span></span>|  
|<span data-ttu-id="07496-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="07496-392">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-392">String</span></span>|  
|<span data-ttu-id="07496-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="07496-394">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-394">String</span></span>|  
|<span data-ttu-id="07496-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="07496-396">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-396">String</span></span>|  
|<span data-ttu-id="07496-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-397">COLLATION_NAME</span></span>|<span data-ttu-id="07496-398">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-398">String</span></span>|  
|<span data-ttu-id="07496-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="07496-400">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-400">String</span></span>|  
|<span data-ttu-id="07496-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="07496-402">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-402">String</span></span>|  
|<span data-ttu-id="07496-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-403">DOMAIN_NAME</span></span>|<span data-ttu-id="07496-404">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-404">String</span></span>|  
|<span data-ttu-id="07496-405">설명</span><span class="sxs-lookup"><span data-stu-id="07496-405">DESCRIPTION</span></span>|<span data-ttu-id="07496-406">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="07496-407">절차</span><span class="sxs-lookup"><span data-stu-id="07496-407">Procedures</span></span>  
  
|<span data-ttu-id="07496-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-408">ColumnName</span></span>|<span data-ttu-id="07496-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="07496-411">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-411">String</span></span>|  
|<span data-ttu-id="07496-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="07496-413">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-413">String</span></span>|  
|<span data-ttu-id="07496-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="07496-415">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-415">String</span></span>|  
|<span data-ttu-id="07496-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="07496-417">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-417">Int16</span></span>|  
|<span data-ttu-id="07496-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="07496-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="07496-419">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-419">String</span></span>|  
|<span data-ttu-id="07496-420">설명</span><span class="sxs-lookup"><span data-stu-id="07496-420">DESCRIPTION</span></span>|<span data-ttu-id="07496-421">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-421">String</span></span>|  
|<span data-ttu-id="07496-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-422">DATE_CREATED</span></span>|<span data-ttu-id="07496-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-423">DateTime</span></span>|  
|<span data-ttu-id="07496-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-424">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="07496-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="07496-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="07496-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-427">ColumnName</span></span>|<span data-ttu-id="07496-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="07496-430">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-430">String</span></span>|  
|<span data-ttu-id="07496-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="07496-432">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-432">String</span></span>|  
|<span data-ttu-id="07496-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="07496-434">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-434">String</span></span>|  
|<span data-ttu-id="07496-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-435">COLUMN_NAME</span></span>|<span data-ttu-id="07496-436">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-436">String</span></span>|  
|<span data-ttu-id="07496-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-437">COLUMN_GUID</span></span>|<span data-ttu-id="07496-438">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-438">Guid</span></span>|  
|<span data-ttu-id="07496-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-439">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-440">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-440">Int64</span></span>|  
|<span data-ttu-id="07496-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="07496-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="07496-442">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-442">Int64</span></span>|  
|<span data-ttu-id="07496-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-444">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-444">Int64</span></span>|  
|<span data-ttu-id="07496-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="07496-445">IS_NULLABLE</span></span>|<span data-ttu-id="07496-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-446">Boolean</span></span>|  
|<span data-ttu-id="07496-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-447">DATA_TYPE</span></span>|<span data-ttu-id="07496-448">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-448">Int32</span></span>|  
|<span data-ttu-id="07496-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-449">TYPE_GUID</span></span>|<span data-ttu-id="07496-450">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-450">Guid</span></span>|  
|<span data-ttu-id="07496-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="07496-452">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-452">Int64</span></span>|  
|<span data-ttu-id="07496-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="07496-454">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-454">Int64</span></span>|  
|<span data-ttu-id="07496-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="07496-456">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-456">Int32</span></span>|  
|<span data-ttu-id="07496-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="07496-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="07496-458">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-458">Int16</span></span>|  
|<span data-ttu-id="07496-459">설명</span><span class="sxs-lookup"><span data-stu-id="07496-459">DESCRIPTION</span></span>|<span data-ttu-id="07496-460">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-460">String</span></span>|  
|<span data-ttu-id="07496-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="07496-461">OVERLOAD</span></span>|<span data-ttu-id="07496-462">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="07496-463">보기</span><span class="sxs-lookup"><span data-stu-id="07496-463">Views</span></span>  
  
|<span data-ttu-id="07496-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-464">ColumnName</span></span>|<span data-ttu-id="07496-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-466">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-467">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-467">String</span></span>|  
|<span data-ttu-id="07496-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-469">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-469">String</span></span>|  
|<span data-ttu-id="07496-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-470">TABLE_NAME</span></span>|<span data-ttu-id="07496-471">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-471">String</span></span>|  
|<span data-ttu-id="07496-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="07496-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="07496-473">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-473">String</span></span>|  
|<span data-ttu-id="07496-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="07496-474">CHECK_OPTION</span></span>|<span data-ttu-id="07496-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-475">Boolean</span></span>|  
|<span data-ttu-id="07496-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="07496-476">IS_UPDATABLE</span></span>|<span data-ttu-id="07496-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-477">Boolean</span></span>|  
|<span data-ttu-id="07496-478">설명</span><span class="sxs-lookup"><span data-stu-id="07496-478">DESCRIPTION</span></span>|<span data-ttu-id="07496-479">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-479">String</span></span>|  
|<span data-ttu-id="07496-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-480">DATE_CREATED</span></span>|<span data-ttu-id="07496-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-481">DateTime</span></span>|  
|<span data-ttu-id="07496-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-482">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="07496-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-484">Indexes</span></span>  
  
|<span data-ttu-id="07496-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-485">ColumnName</span></span>|<span data-ttu-id="07496-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-487">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-488">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-488">String</span></span>|  
|<span data-ttu-id="07496-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-490">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-490">String</span></span>|  
|<span data-ttu-id="07496-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-491">TABLE_NAME</span></span>|<span data-ttu-id="07496-492">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-492">String</span></span>|  
|<span data-ttu-id="07496-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-493">INDEX_CATALOG</span></span>|<span data-ttu-id="07496-494">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-494">String</span></span>|  
|<span data-ttu-id="07496-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="07496-496">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-496">String</span></span>|  
|<span data-ttu-id="07496-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-497">INDEX_NAME</span></span>|<span data-ttu-id="07496-498">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-498">String</span></span>|  
|<span data-ttu-id="07496-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="07496-499">PRIMARY_KEY</span></span>|<span data-ttu-id="07496-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-500">Boolean</span></span>|  
|<span data-ttu-id="07496-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="07496-501">UNIQUE</span></span>|<span data-ttu-id="07496-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-502">Boolean</span></span>|  
|<span data-ttu-id="07496-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="07496-503">CLUSTERED</span></span>|<span data-ttu-id="07496-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-504">Boolean</span></span>|  
|<span data-ttu-id="07496-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-505">TYPE</span></span>|<span data-ttu-id="07496-506">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-506">Int32</span></span>|  
|<span data-ttu-id="07496-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="07496-507">FILL_FACTOR</span></span>|<span data-ttu-id="07496-508">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-508">Int32</span></span>|  
|<span data-ttu-id="07496-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="07496-509">INITIAL_SIZE</span></span>|<span data-ttu-id="07496-510">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-510">Int32</span></span>|  
|<span data-ttu-id="07496-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="07496-511">NULLS</span></span>|<span data-ttu-id="07496-512">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-512">Int32</span></span>|  
|<span data-ttu-id="07496-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="07496-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="07496-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-514">Boolean</span></span>|  
|<span data-ttu-id="07496-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="07496-515">AUTO_UPDATE</span></span>|<span data-ttu-id="07496-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-516">Boolean</span></span>|  
|<span data-ttu-id="07496-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-517">NULL_COLLATION</span></span>|<span data-ttu-id="07496-518">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-518">Int32</span></span>|  
|<span data-ttu-id="07496-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-520">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-520">Int64</span></span>|  
|<span data-ttu-id="07496-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-521">COLUMN_NAME</span></span>|<span data-ttu-id="07496-522">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-522">String</span></span>|  
|<span data-ttu-id="07496-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-523">COLUMN_GUID</span></span>|<span data-ttu-id="07496-524">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-524">Guid</span></span>|  
|<span data-ttu-id="07496-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-525">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-526">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-526">Int64</span></span>|  
|<span data-ttu-id="07496-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-527">COLLATION</span></span>|<span data-ttu-id="07496-528">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-528">Int16</span></span>|  
|<span data-ttu-id="07496-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="07496-529">CARDINALITY</span></span>|<span data-ttu-id="07496-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="07496-530">Decimal</span></span>|  
|<span data-ttu-id="07496-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="07496-531">PAGES</span></span>|<span data-ttu-id="07496-532">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-532">Int32</span></span>|  
|<span data-ttu-id="07496-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="07496-533">FILTER_CONDITION</span></span>|<span data-ttu-id="07496-534">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-534">String</span></span>|  
|<span data-ttu-id="07496-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="07496-535">INTEGRATED</span></span>|<span data-ttu-id="07496-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="07496-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="07496-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="07496-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="07496-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="07496-539">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-539">Tables</span></span>  
  
-   <span data-ttu-id="07496-540">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-540">Columns</span></span>  
  
-   <span data-ttu-id="07496-541">절차</span><span class="sxs-lookup"><span data-stu-id="07496-541">Procedures</span></span>  
  
-   <span data-ttu-id="07496-542">보기</span><span class="sxs-lookup"><span data-stu-id="07496-542">Views</span></span>  
  
-   <span data-ttu-id="07496-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="07496-544">Tables</span><span class="sxs-lookup"><span data-stu-id="07496-544">Tables</span></span>  
  
|<span data-ttu-id="07496-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-545">ColumnName</span></span>|<span data-ttu-id="07496-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-547">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-548">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-548">String</span></span>|  
|<span data-ttu-id="07496-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-550">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-550">String</span></span>|  
|<span data-ttu-id="07496-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-551">TABLE_NAME</span></span>|<span data-ttu-id="07496-552">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-552">String</span></span>|  
|<span data-ttu-id="07496-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-553">TABLE_TYPE</span></span>|<span data-ttu-id="07496-554">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-554">String</span></span>|  
|<span data-ttu-id="07496-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-555">TABLE_GUID</span></span>|<span data-ttu-id="07496-556">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-556">Guid</span></span>|  
|<span data-ttu-id="07496-557">설명</span><span class="sxs-lookup"><span data-stu-id="07496-557">DESCRIPTION</span></span>|<span data-ttu-id="07496-558">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-558">String</span></span>|  
|<span data-ttu-id="07496-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-559">TABLE_PROPID</span></span>|<span data-ttu-id="07496-560">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-560">Int64</span></span>|  
|<span data-ttu-id="07496-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-561">DATE_CREATED</span></span>|<span data-ttu-id="07496-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-562">DateTime</span></span>|  
|<span data-ttu-id="07496-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-563">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="07496-565">Columns</span><span class="sxs-lookup"><span data-stu-id="07496-565">Columns</span></span>  
  
|<span data-ttu-id="07496-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-566">ColumnName</span></span>|<span data-ttu-id="07496-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-568">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-569">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-569">String</span></span>|  
|<span data-ttu-id="07496-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-571">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-571">String</span></span>|  
|<span data-ttu-id="07496-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-572">TABLE_NAME</span></span>|<span data-ttu-id="07496-573">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-573">String</span></span>|  
|<span data-ttu-id="07496-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-574">COLUMN_NAME</span></span>|<span data-ttu-id="07496-575">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-575">String</span></span>|  
|<span data-ttu-id="07496-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-576">COLUMN_GUID</span></span>|<span data-ttu-id="07496-577">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-577">Guid</span></span>|  
|<span data-ttu-id="07496-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-578">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-579">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-579">Int64</span></span>|  
|<span data-ttu-id="07496-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-581">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-581">Int64</span></span>|  
|<span data-ttu-id="07496-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="07496-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-583">Boolean</span></span>|  
|<span data-ttu-id="07496-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="07496-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="07496-585">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-585">String</span></span>|  
|<span data-ttu-id="07496-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="07496-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="07496-587">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-587">Int64</span></span>|  
|<span data-ttu-id="07496-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="07496-588">IS_NULLABLE</span></span>|<span data-ttu-id="07496-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-589">Boolean</span></span>|  
|<span data-ttu-id="07496-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-590">DATA_TYPE</span></span>|<span data-ttu-id="07496-591">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-591">Int32</span></span>|  
|<span data-ttu-id="07496-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-592">TYPE_GUID</span></span>|<span data-ttu-id="07496-593">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-593">Guid</span></span>|  
|<span data-ttu-id="07496-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="07496-595">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-595">Int64</span></span>|  
|<span data-ttu-id="07496-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="07496-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="07496-597">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-597">Int64</span></span>|  
|<span data-ttu-id="07496-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="07496-599">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-599">Int32</span></span>|  
|<span data-ttu-id="07496-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="07496-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="07496-601">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-601">Int16</span></span>|  
|<span data-ttu-id="07496-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="07496-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="07496-603">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-603">Int64</span></span>|  
|<span data-ttu-id="07496-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="07496-605">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-605">String</span></span>|  
|<span data-ttu-id="07496-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="07496-607">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-607">String</span></span>|  
|<span data-ttu-id="07496-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="07496-609">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-609">String</span></span>|  
|<span data-ttu-id="07496-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="07496-611">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-611">String</span></span>|  
|<span data-ttu-id="07496-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="07496-613">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-613">String</span></span>|  
|<span data-ttu-id="07496-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-614">COLLATION_NAME</span></span>|<span data-ttu-id="07496-615">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-615">String</span></span>|  
|<span data-ttu-id="07496-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="07496-617">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-617">String</span></span>|  
|<span data-ttu-id="07496-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="07496-619">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-619">String</span></span>|  
|<span data-ttu-id="07496-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-620">DOMAIN_NAME</span></span>|<span data-ttu-id="07496-621">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-621">String</span></span>|  
|<span data-ttu-id="07496-622">설명</span><span class="sxs-lookup"><span data-stu-id="07496-622">DESCRIPTION</span></span>|<span data-ttu-id="07496-623">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="07496-624">절차</span><span class="sxs-lookup"><span data-stu-id="07496-624">Procedures</span></span>  
  
|<span data-ttu-id="07496-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-625">ColumnName</span></span>|<span data-ttu-id="07496-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="07496-628">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-628">String</span></span>|  
|<span data-ttu-id="07496-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="07496-630">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-630">String</span></span>|  
|<span data-ttu-id="07496-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="07496-632">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-632">String</span></span>|  
|<span data-ttu-id="07496-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="07496-634">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-634">Int16</span></span>|  
|<span data-ttu-id="07496-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="07496-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="07496-636">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-636">String</span></span>|  
|<span data-ttu-id="07496-637">설명</span><span class="sxs-lookup"><span data-stu-id="07496-637">DESCRIPTION</span></span>|<span data-ttu-id="07496-638">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-638">String</span></span>|  
|<span data-ttu-id="07496-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-639">DATE_CREATED</span></span>|<span data-ttu-id="07496-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-640">DateTime</span></span>|  
|<span data-ttu-id="07496-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-641">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="07496-643">보기</span><span class="sxs-lookup"><span data-stu-id="07496-643">Views</span></span>  
  
|<span data-ttu-id="07496-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-644">ColumnName</span></span>|<span data-ttu-id="07496-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-646">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-647">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-647">String</span></span>|  
|<span data-ttu-id="07496-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-649">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-649">String</span></span>|  
|<span data-ttu-id="07496-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-650">TABLE_NAME</span></span>|<span data-ttu-id="07496-651">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-651">String</span></span>|  
|<span data-ttu-id="07496-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="07496-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="07496-653">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-653">String</span></span>|  
|<span data-ttu-id="07496-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="07496-654">CHECK_OPTION</span></span>|<span data-ttu-id="07496-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-655">Boolean</span></span>|  
|<span data-ttu-id="07496-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="07496-656">IS_UPDATABLE</span></span>|<span data-ttu-id="07496-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-657">Boolean</span></span>|  
|<span data-ttu-id="07496-658">설명</span><span class="sxs-lookup"><span data-stu-id="07496-658">DESCRIPTION</span></span>|<span data-ttu-id="07496-659">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-659">String</span></span>|  
|<span data-ttu-id="07496-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="07496-660">DATE_CREATED</span></span>|<span data-ttu-id="07496-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-661">DateTime</span></span>|  
|<span data-ttu-id="07496-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="07496-662">DATE_MODIFIED</span></span>|<span data-ttu-id="07496-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="07496-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="07496-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="07496-664">Indexes</span></span>  
  
|<span data-ttu-id="07496-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="07496-665">ColumnName</span></span>|<span data-ttu-id="07496-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="07496-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="07496-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-667">TABLE_CATALOG</span></span>|<span data-ttu-id="07496-668">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-668">String</span></span>|  
|<span data-ttu-id="07496-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="07496-670">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-670">String</span></span>|  
|<span data-ttu-id="07496-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-671">TABLE_NAME</span></span>|<span data-ttu-id="07496-672">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-672">String</span></span>|  
|<span data-ttu-id="07496-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="07496-673">INDEX_CATALOG</span></span>|<span data-ttu-id="07496-674">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-674">String</span></span>|  
|<span data-ttu-id="07496-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="07496-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="07496-676">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-676">String</span></span>|  
|<span data-ttu-id="07496-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-677">INDEX_NAME</span></span>|<span data-ttu-id="07496-678">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-678">String</span></span>|  
|<span data-ttu-id="07496-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="07496-679">PRIMARY_KEY</span></span>|<span data-ttu-id="07496-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-680">Boolean</span></span>|  
|<span data-ttu-id="07496-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="07496-681">UNIQUE</span></span>|<span data-ttu-id="07496-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-682">Boolean</span></span>|  
|<span data-ttu-id="07496-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="07496-683">CLUSTERED</span></span>|<span data-ttu-id="07496-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-684">Boolean</span></span>|  
|<span data-ttu-id="07496-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="07496-685">TYPE</span></span>|<span data-ttu-id="07496-686">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-686">Int32</span></span>|  
|<span data-ttu-id="07496-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="07496-687">FILL_FACTOR</span></span>|<span data-ttu-id="07496-688">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-688">Int32</span></span>|  
|<span data-ttu-id="07496-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="07496-689">INITIAL_SIZE</span></span>|<span data-ttu-id="07496-690">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-690">Int32</span></span>|  
|<span data-ttu-id="07496-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="07496-691">NULLS</span></span>|<span data-ttu-id="07496-692">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-692">Int32</span></span>|  
|<span data-ttu-id="07496-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="07496-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="07496-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-694">Boolean</span></span>|  
|<span data-ttu-id="07496-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="07496-695">AUTO_UPDATE</span></span>|<span data-ttu-id="07496-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-696">Boolean</span></span>|  
|<span data-ttu-id="07496-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-697">NULL_COLLATION</span></span>|<span data-ttu-id="07496-698">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-698">Int32</span></span>|  
|<span data-ttu-id="07496-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="07496-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="07496-700">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-700">Int64</span></span>|  
|<span data-ttu-id="07496-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="07496-701">COLUMN_NAME</span></span>|<span data-ttu-id="07496-702">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-702">String</span></span>|  
|<span data-ttu-id="07496-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="07496-703">COLUMN_GUID</span></span>|<span data-ttu-id="07496-704">Guid</span><span class="sxs-lookup"><span data-stu-id="07496-704">Guid</span></span>|  
|<span data-ttu-id="07496-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="07496-705">COLUMN_PROPID</span></span>|<span data-ttu-id="07496-706">Int64</span><span class="sxs-lookup"><span data-stu-id="07496-706">Int64</span></span>|  
|<span data-ttu-id="07496-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="07496-707">COLLATION</span></span>|<span data-ttu-id="07496-708">Int16</span><span class="sxs-lookup"><span data-stu-id="07496-708">Int16</span></span>|  
|<span data-ttu-id="07496-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="07496-709">CARDINALITY</span></span>|<span data-ttu-id="07496-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="07496-710">Decimal</span></span>|  
|<span data-ttu-id="07496-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="07496-711">PAGES</span></span>|<span data-ttu-id="07496-712">Int32</span><span class="sxs-lookup"><span data-stu-id="07496-712">Int32</span></span>|  
|<span data-ttu-id="07496-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="07496-713">FILTER_CONDITION</span></span>|<span data-ttu-id="07496-714">문자열</span><span class="sxs-lookup"><span data-stu-id="07496-714">String</span></span>|  
|<span data-ttu-id="07496-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="07496-715">INTEGRATED</span></span>|<span data-ttu-id="07496-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="07496-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07496-717">참고자료</span><span class="sxs-lookup"><span data-stu-id="07496-717">See also</span></span>

- [<span data-ttu-id="07496-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="07496-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
