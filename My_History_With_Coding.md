## My History With Coding

I hadn't seriously started coding until just recently, though my interest in it started many years ago. One major factor in growing my interest is that my dad has worked on software for a healthcare agency from home for most of my life. This has offered me a unique insight into the kinds of day-to-day activities one might have in a career in IT (specifically the path of software development), and continually helps me think about things like how my personal coding habits might affect others I am working with.

When I first started getting on the internet (at about age seven or eight), one of my favorite types of online games were character creators, and eventually I started to get bored just playing them -- I wanted to make them too. I would make my own imitations on paper where I'd have people circle the options they wanted (like low-tech buttons) and then would go draw the character. In retrospect, by doing this I was really trying to simulate simple computer programs before I had any idea of how to make them yet.

In 2011 I discovered Scratch, a free software developed at MIT as a way to get young beginners into coding. I used Scratch all the time for several years to make animations and basic games, such as random name generators or interactive character creators. A little while later I discovered Quest, which allows users to create choose-your-own-path and text adventure types of games, and dabbled in that as well. I believe Quest itself is coded in JavaScript, though I haven't done anything very advanced with it just yet.

At this point, I have had a little bit of experience with HTML and Javascript, and have the most experience in Python since that's the primary language I've been learning to code in.

Here a really simple example program of the kind of thing that I wanted to be able to make when I was younger. There's a lot of room for expanding the existing features and adding more, as well as improving the code itself. This just produces a character with a randomly generated gender, name, age, occupation, and a few traits:

```python

import random

def main():
    generate_character = 'y'
    while generate_character.lower() == 'y':
        
        firstnames_f = ['Alice', 'Bella', 'Crystal', 'Diane', 'Elaine', 'Fiona', 'Ginny', 'Haley', 'Ivy', 'Jo', 'Kelsey', 'Lily', 
        'Monica', 'Nancy', 'Opal', 'Peggy', 'Regina', 'Sally', 'Tiana', 'Veronica', 'Wendy', 'Xara', 'Yolanda', 'Zinnia']
        firstnames_m = ['Alexander', 'Bill', 'Clive', 'Derick', 'Elliott', 'Fred', 'Greg', 'Hal', 'Ivan', 'Jared', 'Kent', 'Lyle', 
        'Mark', 'Nathan', 'Peter', 'Quinn', 'Ryan',
        'Steve', 'Tom', 'Uriah', 'Vincent', 'Wendell', 'Xavier', 'Zane']
        surnames = ['Anderson', 'Barton', 'Caldwell', 'Davis', 'Frank', 'Goldwell', 'Henderson', 'Ingrit', 'Johnson', 'Keppler',
        'Lovett', 'Newkirk', 'Oak', 'Paul', 'Quill', 'River', 'Schmidt', 'Thorton', 'Underhill', 'Violet', 'Weingartz', 'Yolk', 
        'Zimmer']
        occupations = ['an architect', 'a freelancer', 'a chef', 'a flight attendant', 'a nurse', 'a surgeon', 'a lawyer', 
        'a waitress', 'an engineer', 'a consultant', 'a data scientist', 'a mechanic', 'a gym trainer', 'a farmer', 
        'a real estate agent', 'unemployed']
        all_traits = ['lazy', 'active', 'a neat freak', 'a slob', 'rude', 'polite', 'impatient', 'sensitive', 'a foodie', 'vegan', 
        'caring', 'funny', 'family-oriented', 'artistic', 'a dog lover', 'a cat lover', 'a nerd', 'shy', 'talkative']
        
        if random.randint(0, 1) == 0:
            gender = ('Woman', 'Her', 'She', 'Hers')
            name = firstnames_f[random.randint(0, len(firstnames_f) - 1)] + ' ' + surnames[random.randint(0, len(surnames) - 1)]
        else:
            gender = ('Man', 'Him', 'He', 'His')
            name = firstnames_m[random.randint(0, len(firstnames_m) - 1)] + ' ' + surnames[random.randint(0, len(surnames) - 1)]
        age = random.randint(20, 55)
        job = occupations[random.randint(0, len(occupations) - 1)]
        
        traits = []
        for n in range(3):
            random_trait = all_traits[random.randint(0, len(all_traits) - 1)]
            traits.append(all_traits.pop(all_traits.index(random_trait)))
            if random_trait == 'lazy':
                all_traits.remove('active')
            if random_trait == 'active':
                all_traits.remove('lazy')
            if random_trait == 'a neat freak':
                all_traits.remove('a slob')
            if random_trait == 'a slob':
                all_traits.remove('a neat freak')
            if random_trait == 'rude':
                all_traits.remove('polite')
            if random_trait == 'polite':
                all_traits.remove('rude')
        
        print()
        print(name, 'is a', str(age) + '-year-old', gender[0].lower(), 'who is', job + '.')
        print(gender[2], 'is', traits[0] + ',', traits[1] + ', and', traits[2] + '.')
        
        generate_character = input('\nDo you want to generate another character? ')

main()


```

[_<<Back_](Volunteerwork_and_Community_Involvement.md "volunteerwork and etc.") [Home](README.md) [_Next>>_](Hobbies_and_Interests.md "hobbies and interests")
