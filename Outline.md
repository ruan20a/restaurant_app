# Problem
Yelp returns the most popular + high-volume reviewed restaurants to help us make choices but it often overwhelms and stops us from making quick choices. I want to make a listing service based on the top 10 favorite from friends that focuses on 4 keys to help us make quicker decisions. 

#Bare Minimum 
- Restaurant List
- Group <=> Users Work
- List <=> Users <=> Restaurants Work 

#Outline
1. Databases Tables
	A. Users 
		1. Attributes
			a. :name, :email, :password_digest, :timestamps
			b. has_secure_password
		2. Relationships 
			a. has_many :memberships
			b. has_many :groups through:membershosp
			c. has_many :favorites
			d. has_many :restaurants throught:favorites
	B. Groups
		1. Attributes
			a. :name,:timestamps,
		2. Relationships
			a. has_many :memberships
			b. has_many :users through: :memberships
	C. Memberships
		1. Attributes
			a. :user_id, :group_id, :creator, :timestamps
		2. Relationships
			a. belongs_to :users
			b. belongs_to :groups
	D. Restaurants
		1. Attributes
			a :name :address :lat :lng :photo_ref, :is_open
		2. Relationships
			a. has_many :favorites
			b. has_many :users through: :favorites
	E. Favorites 
		1. Attributes
			a :users_id, :restaurant_id, 
			:cuisine, :price, :atmosphere, :awesome_for,
		2. Relationships
			a. belongs_to :users
			b. belongs_to :restaurants
	
IMPORTANT NEED TO FIGURE OUT STEPS 
4. Extract Restaurant Informations
	A. Figure out GOOGLE:API!
5. Test out create User
6. Test out User <=> Groups <=> Memberships
7. Test out if Choices is working (pairing up users with restaurants)
8. Test out if you can add choice => move to favorite form (fill out favorites) => add to lists which matches to users and shows up to users!!
9. Make it pretty and intuitive
10. Neighborhood Gem || Fanciest Pick || Go-To Spot || Hole in the Wall || Top Pick 