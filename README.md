def generate_abstract(problem, methods, results, implications, keywords):
  
    abstract = f"{problem} {methods} {results} {implications}"
    
    
    word_count = len(abstract.split())
    if word_count > 300:
        print(f"Warning: Abstract is {word_count} words. Please reduce to 300 or fewer words.")
    
    
    formatted_keywords = "Keywords: " + ", ".join(keywords)
    
    return abstract, formatted_keywords


if __name__ == "__main__":
    print("Enter each part of the abstract below.\n")
    
    problem = input("1. Problem explanation: ").strip()
    methods = input("2. Methods used: ").strip()
    results = input("3. Significant results: ").strip()
    implications = input("4. Implications for the field: ").strip()
    
    #
    keywords_input = input("Enter 3 to 7 keywords (comma separated): ").strip()
    keywords = [kw.strip() for kw in keywords_input.split(",") if kw.strip()]
    
    if not (3 <= len(keywords) <= 7):
        print("Error: You must enter between 3 and 7 keywords.")
    else:
        abstract, keyword_line = generate_abstract(problem, methods, results, implications, keywords)
        print("\n--- Generated Abstract and Keywords ---")
        print("\nAbstract:")
        print(abstract)
        print("\n" + keyword_line)
