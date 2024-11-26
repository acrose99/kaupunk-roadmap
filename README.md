# Alpha Roadmap

## Payments/Compliance
- [ ] Subscriptions
	- [ ] Integrate with Stripe Checkout and Stripe Billing
	- [ ] Stripe Billing/Checkout Docs: https://docs.stripe.com/billing/subscriptions/build-subscriptions?platform=web&ui=stripe-hosted
		- [ ] We need a Monthly and a Yearly Subscription
	- [ ] We should have a Web Hook where any time a user space, location, category, or general suggestion is accepted, we give them a month off for free using Stripe. 
- [ ] Transparency Trackers
	- [ ] Donation Tracker: 2-4k in Donations publicly available based on donating the 10% of all Profit. 
	- [ ] Profit Transparency: Visualize how every subscription is monetized: 
		- **Expenses for every 5 dollars**
			- 45c to Stripe
			- 50c saved to donate to non profit
			- [ ] Determine Other Sources here
			- [ ] This means 80% goes to paying for expenses to maintain the site and to support the team. 
		- **General Expenses**
			- **Backend**: $20 a month to Supabase for their BaaS (Backend as a service)
			- **Hosting**: 
				- $20 a month to Vercel for their Pro Plan
				- $6 a month to Digital Ocean for their VPS to perform automatic actions. 
	- [ ] Open Source:
		- [ ] We Aim to Open Source isolated aspects of our Technical Architecture when it's safe to do so; in other words it needs to be reviewed to make sure no flaws that could harm our users are exposed. 
		- [ ] Potential things to Open Source
			- [ ] The UI and ways we calculate the six different safety scores
			- [ ] Custom Tip Tap Editor Instance
			- [ ] Donation Tracker source code

## Frontend
- [ ] Public Content
	- [x] Main "Explore" View
		- [x] Search for Locations, Spaces, Categories
		- [x] Cards, Map, Table View
	- [ ] Locations
		- [ ] Location Detail Page
			- [ ] Need to redesign this. 
	- [x] Spaces
		- [x] Dedicated Spaces Filter
		- [x] Public Space Detail Page 
	- [x] Categories
		- [x] Dedicated Categories Page with a view of all categories 
		- [x] Category Detail Page
	- [x] Featured Content
		- [x] Featured Spaces
		- [x] Featured Location
	- [ ] About
		- [ ] Mission Statement
			- Mostly Done. Refactor Once
		- [ ] Comparison Page
		- [ ] Team Page 
		- [ ] Transparency Trackers (see payment section for details)
			- [ ] Donation Tracker Page
			- [ ] Profit Transparency Page
	- [ ] Misc Stuff like Privacy Policy, Site Map, etc
- [ ] Admin Content
	- [ ] Admin Dashboard
		- [x] Manual Editing/Creating
			- [x] Dashboard of the following
			- [x] Locations
				- [x] Create Locations
				- [x] Edit Locations
			- [x] Spaces
				- [x] Create Spaces
				- [x] Edit Spaces
			- [x] Categories
				- [x] Create Categories
				- [x] Edit Categories
		- [ ] Automatic Suggestions (need to deploy this to docker)
			- [ ] Edit Locations
				- mostly done other then deploymenet
			- [ ] Edit Public Spaces
			- [ ] Categories
				- [ ] Create Categories
				- [ ] Edit Categories
		- [ ] User Management
			- [ ] Delete/Edit/View Users through UI
		- [ ] Data Management
			- [ ] View Data Sources and Generate New Data
	- [x] Admin have access to correct permissions using Next_Auth, the rest is completely limited. 
- [ ] User Content (I need to merge the PR and most of this will be complete)
	- [x] ~~User Content Preferences (I'm Scrapping This for Now)~~
	- [ ] User Dashboard
		- [x] Overview/Home
		- [x] Contributions/Reporting
			- [x] General: 
				- [x] Reporting an Issue
				- [x] Suggesting a general issue
			- [x] Suggesting New Content
				- [x] Suggesting New Locations
				- [x] Suggesting New Spaces
				- [x] Suggesting New Categories
			- [ ] When they suggest any new content or a general suggestion is tracked, it should trigger a free plan
		- [x] Saved Locations View (refactor this)
		- [x] Spaces
			- [x] Create Space
			- [x] Saved/Created Spaces View
		- [x] Profile
			- [x] Edit Bio
		- [x] Saved Preferences
			- [x] Theming
			- [ ] ~~Map Setting (I'm Scrapping This for Now)~~
## Backend 

### Data Management/Flask
- [ ] Automatic Suggestions (need to deploy this to docker)
	- [ ] Edit Locations
		- mostly done other then deploymenet
	- [ ] Edit Public Spaces
	- [ ] Categories
		- [ ] Create Categories
		- [ ] Edit Categories
### Database/Supabase
- [x] Have Scheduled Backups 
- [ ] ~~Have better caching for buckets (not in beta)

### Image Optimization (not in beta)
- [ ] Before any images are uploaded, optimize them 
## Security

- [ ] Ensure every single table has RLS enabled with the correct permissions
- [ ] Make the ID for any publicly editable table uneditable. 
	- [ ] I.E Users, Suggestions/Contributions, User Spaces
- [ ] Ensure proper rate limiting 
	- [ ] add alert when triggered
- [ ] add robots.tx 
